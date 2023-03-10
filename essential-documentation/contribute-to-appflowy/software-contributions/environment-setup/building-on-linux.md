# 🐧 Building on Linux

**Notes:**

* The following steps are verified on
  * [x] Lubuntu 20.04 - x86\_64
  * [x] Linux Mint 20.3 - x86\_64
  * [ ] Ubuntu 20.04 - aarch64
  * [ ] Redhat Linux - x86\_64
  * [x] Fedora 37 - x86\_64
  * [x] Arch Linux - x86\_64
  * [ ] Deepin - x86\_64
  * [ ] Raspberry Pi OS - aarch64
* You may need to disable hardware 3D acceleration if you are running AppFlowy in a VM. Otherwise, certain GL failures will prevent the app from launching.
* This guide assumes that you are using the **bash** shell on Linux. You can however, replicate these steps on **zsh** or other alternative Linux terminal shells, with minor alterations.

{% hint style="warning" %}
**If you encounter any issues, have a look at** [**Troubleshooting**](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup/trouble-shotting) **first. If your issue is not included in the page, please create an** [**issue**](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) **or ask on** [**Discord**](https://discord.gg/9Q2xaN37tV)**.**
{% endhint %}

{% hint style="danger" %}
**There is a known issue with Ubuntu 22.04, Fedora 37, and PopOS 22.04:**



`Failed to load dynamic library 'libdart_ffi.so': libssl.so.1.1: cannot open shared object file: No such file or directory.`\
``\
``The issue can be fixed by installing the required missing libraries:

```bash
# Fedora Workstation
sudo dnf install openssl-devel
```

```bash
# Fedora Silverblue
rpm-ostree upgrade && rpm-ostree install openssl1.1.x86_64 # Silverblue
```

```bash
# Ubuntu & PopOS
wget http://archive.ubuntu.com/ubuntu/pool/main/o/openssl/libssl1.1_1.1.0g-2ubuntu4_amd64.deb
sudo dpkg -i libssl1.1_1.1.0g-2ubuntu4_amd64.deb
```

If the above Ubuntu & PopOS link is expired, or returns an error 404 then consider searching for libssl1.1\_1.1.1 on the following [page](http://nz2.archive.ubuntu.com/ubuntu/pool/main/o/openssl/?C=M;O=D).
{% endhint %}

### Step 1: Get the source code

Clone the source code from our Github project.

```shell
git clone https://github.com/AppFlowy-IO/AppFlowy.git
```

{% hint style="warning" %}
Ensure that git is installed in your system!! Use your package manager to install git if your distribution doesn't ship with git.

```bash
# Ubuntu
sudo apt install git
```

```bash
# Fedora
sudo dnf install git
```

```bash
# Arch
sudo pacman -S git
```
{% endhint %}

{% hint style="info" %}
You should fork the code instead if you wish to submit code to AppFlowy. You will find information on that in [Setting Up Your Repositories](../submitting-code/setting-up-your-repositories.md).
{% endhint %}

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 13-51-27 (1).png" alt=""><figcaption><p>Image: Cloning the source  from the Github repository. </p></figcaption></figure>

### Step 2: Install your build environment

#### **Install system prerequisites:**

{% tabs %}
{% tab title="Ubuntu" %}
```bash
sudo apt-get install curl build-essential libsqlite3-dev libssl-dev clang cmake ninja-build pkg-config libgtk-3-dev unzip libkeybinder-3.0-dev
```
{% endtab %}

{% tab title="Fedora" %}
```bash
sudo dnf install sqlite-devel keybinder3-devel clang cmake ninja-build openssl-devel
```
{% endtab %}

{% tab title="Arch" %}
```bash
sudo pacman -S curl base-devel sqlite openssl clang cmake ninja pkg-config gtk3 unzip libkeybinder3 xdg-user
```
{% endtab %}
{% endtabs %}

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 13-32-41.png" alt=""><figcaption><p>Image: Installing prerequisites on Ubuntu.</p></figcaption></figure>

#### **Install flutter (three different methods):**

{% hint style="danger" %}
Flutter version 3.3.10 is the recent supported stable release used for for building AppFlowy. Building with the latest stable Flutter release is not tested and might throw errors while building.
{% endhint %}

* **Method 1:** Install flutter according to [https://docs.flutter.dev/get-started/install/linux](https://docs.flutter.dev/get-started/install/linux). Make sure to install flutter in a directory that is appropriate for you.
* **Method 2:** You can use the code below to install flutter manually on your linux system.

```bash
git clone https://github.com/flutter/flutter.git --branch 3.3.10
cd flutter
echo -e "\nexport PATH=\$PATH:"`pwd`"/bin" >> ~/.bashrc
source ~/.bashrc
flutter
cd ..
```

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 13-55-23.png" alt=""><figcaption><p>Image: Installing flutter manually.</p></figcaption></figure>

* **Method 3**: You can also use a runtime version manager like [asdf](https://asdf-vm.com/) or a flutter-specific version manager to install flutter on your system. Assuming you are using the **bash** shell, follow these steps:

1. Clone asdf.

```bash
git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.11.1
```

2. Add the path to asdf and enable asdf auto-completion in your shell.

```bash
echo -e '\n# asdf configuration \n. "$HOME/.asdf/asdf.sh"\n. "$HOME/.asdf/completions/asdf.bash"' >> ~/.bashrc
source ~/.bashrc
```

{% hint style="warning" %}
If you are not using **bash**, check the official [asdf guide](https://asdf-vm.com/guide/getting-started.html) to learn how to set up asdf for your shell.
{% endhint %}

3. Install  flutter via asdf and set it as your local runtime at the AppFlowy source directory (`xx/AppFlowy/`). &#x20;

```bash
cd AppFlowy
asdf plugin-add flutter
asdf install flutter 3.3.10-stable
rm -rf .tool-versions
asdf local flutter 3.3.10-stable 
cd ..
```

{% hint style="warning" %}
Some distributions might miss certain packages essential for asdf, such as `jq`, `curl`, or `wget`. Please make sure they are installed via your package manager.\
\
👉 **Ubuntu 22.04** does not come with the package `jq` installed by default, you will have to install by doing:

```bash
sudo apt install jq
```
{% endhint %}

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 22-39-23.png" alt=""><figcaption><p>Image: Installing flutter using asdf</p></figcaption></figure>

#### **Setting up your development environment**:

Run the setup script from the base directory. (**Note:** You can skip this step if you installed rust using asdf and set it as the local runtime inside the`xx/AppFlowy/` source.)

```bash
cd AppFlowy
./frontend/scripts/install_dev_env/install_linux.sh
source ~/.bashrc
```

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 22-43-35.png" alt=""><figcaption><p>Image: Running script  install_linux.sh inside <code>xx/AppFlowy/frontend/scripts/install_dev_env/</code>.</p></figcaption></figure>

{% hint style="warning" %}
**If you get this following warning (image shown below** 👇**):**

****

`Warning: Pub installs executables into $HOME/.pub-cache/bin, which is not on your path. You can fix that by adding this to your shell's config file (.bashrc, .bash_profile, etc.):`

`export PATH="$PATH":"$HOME/.pub-cache/bin"`\
\
Run following command to add the path inside your shell configuration dotfile (`.bashrc`, `.zshrc`, etc.). For **bash** users:

```bash
echo -e '\nexport PATH="$PATH":"$HOME/.pub-cache/bin"' >> ~/.bashrc
source ~/.bashrc
```

OR, you can alternatively do this:

```bash
export PATH="$PATH":"$HOME/.pub-cache/bin
```
{% endhint %}

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 20-44-39.png" alt=""><figcaption><p>Image: <code>"Warning: Pub installs executables into $HOME/.pub-cache/bin, which is not on your path."</code></p></figcaption></figure>

### Step 3: Build AppFlowy (Flutter GUI application)

Change your path to the `frontend` directory.

```bash
cd frontend
```

#### Building the AppFlowy binary:

{% tabs %}
{% tab title="Release binary" %}
```bash
cargo make --profile production-linux-x86_64 appflowy 
```
{% endtab %}

{% tab title="Debug binary" %}
```bash
cargo make --profile development-linux-x86_64 appflowy-dev 
```
{% endtab %}
{% endtabs %}

You will find the binary in `frontend/appflowy_flutter/product/[version in x.x.x]/linux/[Binary type (Release/ Debug)]/AppFlowy/`.

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 23-03-46.png" alt=""><figcaption><p>Image: Building AppFlowy</p></figcaption></figure>

### Step 4: Run the application

#### For running the release binary:

```bash
cd appflowy_flutter/product/[version number in x.x.x]/linux/Release/AppFlowy
./app_flowy
```

#### For running the debug binary:

```bash
cd appflowy_flutter/product/[version number in x.x.x]/linux/Debug/AppFlowy
./app_flowy
```

{% hint style="info" %}
If you do not know the version number for the AppFlowy binary that you have built, please use your terminal shells' tab completion, or type and enter the`ls`(list) command to reveal the name of folder which is the version number you are building.

**The current version of AppFlowy is 0.1.0.**&#x20;
{% endhint %}

A new window as shown below will show up after you run the application:

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-02-27 21-59-56 (1).png" alt=""><figcaption><p>Image: AppFlowy window</p></figcaption></figure>

If using a virtual machine, run the Linux GUI application through x11 on windows (use MobaXterm) for instance:

`export DISPLAY=localhost:10`

### Miscellaneous: Running the application without building (using VS Code)

{% hint style="warning" %}
**Do not use the flatpak distribution of VS Code!**\
****The flatpak VS Code is sandboxed and uses an isolated shell environment, and cannot access any binaries or libraries installed in your system, including your default system shell.
{% endhint %}

1. Open the `frontend` folder located at `xx/AppFlowy/` with VS Code.
2. Go to the Run and Debug tab and then click AF-desktop: Clean + Rebuild All for the first time running.

![Image: Running the application using VS Code](../../../../.gitbook/assets/launch\_appflowy.png)
