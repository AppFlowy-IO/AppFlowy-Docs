# 🪟 Building on Windows

**Notes:**

* The following steps are verified on
  * [x] Windows 10 X86\_64
  * [ ] Windows 10 arm64
  * [x] Windows 11 X86\_64
  * [ ] Windows 11 arm64
* Both Windows `cmd` and `powershell` can be used for running commands.
* If you encounter any issues, please have a look at [Troubleshooting](https://github.com/AppFlowy-IO/appflowy/wiki/Troubleshooting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## Step 1: Get the source code

{% hint style="warning" %}
You should fork the code instead if you wish to submit patches. You'll find information on that in [setting-up-your-repositories.md](../submitting-code/setting-up-your-repositories.md "mention")
{% endhint %}

```shell
git clone https://github.com/AppFlowy-IO/appflowy.git
```

## Step 2: Install your build environment

* Install Visual Studio 2022 build tools. Download from [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/)
  * In section "All Downloads" => "Tools for Visual Studio 2022" => "Build Tools for Visual Studio 2022".
  * Launch `vs_BuildTools.exe` to install.
    * Choose "Desktop Development with C++"
* Install vcpkg according to [this page](https://github.com/microsoft/vcpkg#quick-start-windows). Make sure to add vcpkg installation folder to your [PATH environment variable](https://helpdeskgeek.com/windows-10/add-windows-path-environment-variable/).
* Install flutter according to [this page](https://docs.flutter.dev/get-started/install/windows).
* Make sure to enable the flutter stable channel

```shell
flutter channel stable
```

* Enable the specified platform first if you don't enable it before and then select the desktop device.

```
flutter config --enable-windows-desktop
```

* Fix any problems reported by flutter doctor

```shell
flutter doctor
```

* Install rust
  * Download `rustup.exe` from [https://win.rustup.rs/x86\_64](https://win.rustup.rs/x86\_64)
  * Call rustup.exe from powershell or cmd

```shell
.\rustup-init.exe --default-toolchain stable --default-host x86_64-pc-windows-msvc -y
```

* Install cargo make

{% hint style="info" %}
You probably need to re-open your terminal to get the `cargo` command in your PATH
{% endhint %}

```shell
cd AppFlowy/frontend
```

```shell
cargo install --force cargo-make
```

* Install duckscript

```shell
cargo install --force duckscript_cli
```

* Add Powershell to the PATH

Add `C:\Windows\System32` to the PATH to prevent Powershell build commands crashing.

* Install openssl
  * Download `openssl_1.1.1n_win32_complete.zip` from [https://sockettools.com/kb/openssl-installation-packages-windows/](https://sockettools.com/kb/openssl-installation-packages-windows/)
  * Run installer and install Openssl where you want
  * Add `bin` folder to the PATH (ie: `G:\Compilation\OpenSSL\bin`)
  * Create a new User variable (using the same window as the PATH editor): Name it `OPENSSL_DIR` with same value as bin folder (ie `G:\Compilation\OpenSSL\bin`)

* Install perl
  * Download Perl for Windows (called Strawberry perl) from [https://strawberryperl.com/](https://strawberryperl.com/) (choose x64 installer)
  * Run installer
  * Check Perl is installed with following command

```shell
perl --version
```

* Install Dart extension for Visual Studio Code

* Enable the Dart `protoc_plugin`

```shell
dart pub global activate protoc_plugin
```

* For Windows 11: Activate Developer Mode
  * Go to Settings > Privacy & Security > switch ON Developer Mode

## Step 3: Edit and run the application

\[VS Code]

1. Open the `frontend` folder located at xx/AppFlowy/frontend with VS Code.
2. Go to the Run and Debug tab and then click AF-desktop: Clean + Rebuild All for the first time running.

![img.png](../../../../.gitbook/assets/launch\_appflowy.png)

If you encounter any issues, have a look at [Troubleshooting](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup/trouble-shotting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## Building in release mode

1. Go to the AppFlowy/frontend/ directory.
2. Run the following command to create the binary.

```bash
cargo make --profile production-windows-x86 appflowy
```

The scripts are located in the AppFlowy/frontend/Makefile.toml file.

The resulting binary file is located in `AppFlowy/frontend/app_flowy/product/x.x.x/Windows/Release/AppFlowy/`.

If using a virtual machine

* Run Linux GUI application through x11 on windows (use MobaXterm) for instance:

`export DISPLAY=localhost:10`
