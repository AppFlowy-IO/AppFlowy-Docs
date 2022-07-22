# 🐧 Building on Linux

**Notes:**

* The following steps are verified on
  * [x] lubuntu 20.04 - X86\_64
  * [ ] ubuntu 20.04 - aarch64
  * [ ] redhat - X86\_64
  * [x] Arch Linux - X86\_64
  * [ ] Deepin - X86\_64
  * [ ] Raspberry Pi OS - aarch64
  * [x] openSUSE Tumbleweed - x86\_64
* You may need to disable hardware 3D acceleration if you are running AppFlowy in a VM. Otherwise, certain GL failures will prevent the app from launching.
* If you encounter any issues, have a look at [troubleshooting-when-installing-appflowy.md](../../../install-appflowy/installation-methods/troubleshooting-when-installing-appflowy.md "mention") first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## Step 1: Get the source code

Clone the source code from our Github project.

{% hint style="warning" %}
You should fork the code instead if you wish to submit code to AppFlowy. You'll find information on that in [setting-up-your-repositories.md](../submitting-code/setting-up-your-repositories.md "mention")
{% endhint %}

```shell
git clone https://github.com/AppFlowy-IO/appflowy.git
```

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
yay -S curl base-devel sqlite openssl clang cmake ninja pkg-config gtk3 unzip
```
{% endtab %}

{%tab title="openSUSE Tumbleweed" %}
```bash
sudo zypper install -t pattern devel_basis
sudo zypper install libopenssl-devel sqlite3-devel clang cmake ninja pkgconf-pkg-config pkgconf libgtk-3-0 curl zip unzip gtk3-devel
```
{% endtab %}

{% endtabs %}

* Install Rust according to [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install). 

* Install the required Rust components

```bash
rustup toolchain install stable
rustup component add cargo
cargo install cargo-make

```


* Install flutter according to [https://docs.flutter.dev/get-started/install/linux](https://docs.flutter.dev/get-started/install/linux). Make sure to install flutter in a directory that is appropriate for you.

```bash
git clone https://github.com/flutter/flutter.git
cd flutter
echo "export PATH=\$PATH:"`pwd`"/bin" >> ~/.profile
export PATH="$PATH:`pwd`/bin"
```

* Run the setup script from the base directory
```bash
./frontend/scripts/install_dev_env/install_linux.sh
```

## Step 3: Build AppFlowy (Flutter GUI application)

* Change to the frontend directory

```bash
cd AppFlowy/frontend
```

* \[Optional] Build flowy-sdk-dev (dart-ffi)

{% tabs %}
{% tab title="Development" %}
```bash
cargo make --profile development-linux-x86_64 flowy-sdk-dev
```
{% endtab %}

{% tab title="Production" %}
```bash
cargo make --profile production-linux-x86_64 flowy-sdk-release
```
{% endtab %}
{% endtabs %}

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

## Step 4: Run the application

```bash
cd app_flowy/product/0.0.2/linux/Debug/AppFlowy
```

```shell
./app_flowy
```

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
