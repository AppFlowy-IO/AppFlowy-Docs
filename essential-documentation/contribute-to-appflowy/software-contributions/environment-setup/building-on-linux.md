# 🐧 Building on Linux

**Notes:**

* The following steps are verified on
  * [x] lubuntu 20.04 - X86\_64
  * [x] Linux Mint 20.3 - 86\_64
  * [ ] ubuntu 20.04 - aarch64
  * [ ] redhat - X86\_64
  * [x] Arch Linux - X86\_64
  * [ ] Deepin - X86\_64
  * [ ] Raspberry Pi OS - aarch64
* You may need to disable hardware 3D acceleration if you are running AppFlowy in a VM. Otherwise, certain GL failures will prevent the app from launching.
* If you encounter any issues, have a look at [troubleshooting-when-installing-appflowy.md](../../../install-appflowy/installation-methods/troubleshooting-when-installing-appflowy.md "mention") first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

{% hint style="warning" %} There is a known issue with Ubuntu 22.04, Fedora 36, and PopOS 22.04: 
`Failed to load dynamic library 'libdart_ffi.so': libssl.so.1.1: cannot open shared object file: No such file or directory`
The issue can be fixed by installing the required missing libraries:
```
# Fedora
sudo dnf in openssl1.1.x86_64 # Workstation
rpm-ostree upgrade && rpm-ostree install openssl1.1.x86_64 # Silverblue

# Ubuntu & PopOS
$ wget http://nz2.archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.1f-1ubuntu2.16_amd64.deb
$ sudo dpkg -i libssl1.1_1.1.1f-1ubuntu2.16_amd64.deb
```

If the above ``Ubuntu & PopOS`` link is expired or returns 404 then consider searching for ``libssl1.1_1.1.1`` on the following [page](http://nz2.archive.ubuntu.com/ubuntu/pool/main/o/openssl/?C=M;O=D).

{% endhint %}

## Step 1: Get the source code

Clone the source code from our Github project.

{% hint style="warning" %}
You should fork the code instead if you wish to submit code to AppFlowy. You'll find information on that in [setting-up-your-repositories.md](../submitting-code/setting-up-your-repositories.md "mention")
{% endhint %}

```shell
git clone https://github.com/AppFlowy-IO/appflowy.git
```
![img.png](../../../../.gitbook/assets/build\_step\_one.png)

## Step 2: Install your build environment

Feel free to ask questions on our [Discord](https://discord.gg/9Q2xaN37tV) so that we may refine this document and make the process as easy as possible for you.

* Install system prerequisites

{% tabs %}
{% tab title="Ubuntu" %}
```bash
sudo apt-get install curl build-essential libsqlite3-dev libssl-dev clang cmake ninja-build pkg-config libgtk-3-dev unzip
```

{% endtab %}

{% tab title="Arch" %}
```bash
sudo pacman -S curl base-devel sqlite openssl clang cmake ninja pkg-config gtk3 unzip libkeybinder3 xdg-user-dirs
```
{% endtab %}
{% endtabs %}

![img.png](../../../../.gitbook/assets/build\_step\_two.png)

* Install flutter according to [https://docs.flutter.dev/get-started/install/linux](https://docs.flutter.dev/get-started/install/linux). Make sure to install flutter in a directory that is appropriate for you.

* Or you can use the code below to install `FLUTTER` manually on your linux system.

```bash
git clone https://github.com/flutter/flutter.git
cd flutter
echo "export PATH=\$PATH:"`pwd`"/bin" >> ~/.profile
export PATH="$PATH:`pwd`/bin"
cd ..
```
![img.png](../../../../.gitbook/assets/flutter\_build\_step.png)

* Run the setup script from the base directory
```bash
cd appflowy
./frontend/scripts/install_dev_env/install_linux.sh
```
![img.png](../../../../.gitbook/assets/build\_step\_two\_script.png)

![img.png](../../../../.gitbook/assets/build\_step\_two\_warn\_success.png)

`If you get the warning as shown above, run following command:`

```bash
export PATH="$PATH":"$HOME/.pub-cache/bin"
```

## Step 3: Build AppFlowy (Flutter GUI application)

* Change to the frontend directory

```bash
cd frontend
```

* `Optionally if you want to Build appflowy-sdk-dev (dart-ffi)`

{% tabs %}
{% tab title="Development" %}
```bash
cargo make --profile development-linux-x86_64 appflowy-sdk-dev 
```

{% endtab %}

{% tab title="Production" %}
```bash
cargo make --profile production-linux-x86_64 appflowy-sdk-release
```

{% endtab %}
{% endtabs %}

![img.png](../../../../.gitbook/assets/build\_step\_optional\_three\_success.png)

* Build AppFlowy. You'll find the binary in app\_flowy/product/linux/AppFlowy/

{% tabs %}
{% tab title="Development" %}
```
cargo make -p development-linux-x86_64 appflowy-linux-dev
```
{% endtab %}

{% tab title="Production" %}

```bash
cargo make -p production-linux-x86_64 appflowy-linux
```
{% endtab %}
{% endtabs %}

![img.png](../../../../.gitbook/assets/build\_step\_three\_success.png)

## Step 4: Run the application

```bash
cd app_flowy/product/0.0.5/linux/Debug/AppFlowy
```

```shell
./app_flowy
```
![img.png](../../../../.gitbook/assets/build\_step\_four\_success.png)

* A new window as shown below will show up after you run the application:

![img.png](../../../../.gitbook/assets/welcome\_screen.png)


* If using a virtual machine
  * Run Linux GUI application through x11 on windows (use MobaXterm) for instance:

`export DISPLAY=localhost:10`

## Step 5: Edit and run the application

\[VS Code]

1. Open the `frontend` folder located at xx/AppFlowy/frontend with VS Code.
2. Go to the Run and Debug tab and then click AF: Clean + Rebuild All for the first time running.

![img.png](../../../../.gitbook/assets/launch\_appflowy.png)

If you encounter any issues, have a look at [Troubleshooting](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup/trouble-shotting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## Building in release mode

1. Go to the AppFlowy/frontend/ directory.
2. Run the following command to create the binary.

```bash
cargo make --profile production-linux-x86 appflowy
```

The scripts are located in the AppFlowy/frontend/Makefile.toml file.

The resulting binary file is located in `AppFlowy/frontend/app_flowy/product/x.x.x/linux/Release/AppFlowy/`.
