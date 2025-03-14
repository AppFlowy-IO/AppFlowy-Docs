# 🪟 Building on Windows

**Notes:**

- The following steps are verified on
  - [x] Windows 10 X86_64
  - [ ] Windows 10 arm64
  - [x] Windows 11 X86_64
  - [ ] Windows 11 arm64
- Both Windows `cmd` and `powershell` can be used for running commands.
- If you encounter any issues, please have a look at [Troubleshooting](https://github.com/AppFlowy-IO/appflowy/wiki/Troubleshooting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).\

**If you prefer a video tutorial click here:**&#x20;

{% embed url="https://www.youtube.com/watch?v=RhyTyNZuAFo" %}
video tutorial for building on windows&#x20;
{% endembed %}

## Step 1: Get the source code

{% hint style="warning" %}
You should fork the code instead if you wish to submit patches. You'll find information on that in [setting-up-your-repositories.md](../../../../essential-documentation/contribute-to-appflowy/software-contributions/submitting-code/setting-up-your-repositories.md "mention")
{% endhint %}

```shell
git clone https://github.com/AppFlowy-IO/appflowy.git
```

## Step 2: Install your build environment

- Install Visual Studio 2022 build tools. Download from [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/)
  - In section "All Downloads" => "Tools for Visual Studio 2022" => "Build Tools for Visual Studio 2022".
  - Launch `vs_BuildTools.exe` to install.
    - Choose "Desktop Development with C++"
- Install vcpkg according to [this page](https://github.com/microsoft/vcpkg#quick-start-windows). Make sure to add vcpkg installation folder to your [PATH environment variable](https://helpdeskgeek.com/windows-10/add-windows-path-environment-variable/).
- Install flutter according to [this page](https://docs.flutter.dev/get-started/install/windows).
- Make sure to use the Flutter 3.27.4 version

```shell
flutter --version
Flutter 3.27.4 • channel stable • https://github.com/flutter/flutter.git
Framework • revision d8a9f9a52e (4 weeks ago) • 2025-01-31 16:07:18 -0500
Engine • revision 82bd5b7209
Tools • Dart 3.6.2 • DevTools 2.40.3
```

- Enable the specified platform first if you don't enable it before and then select the desktop device.

```
flutter config --enable-windows-desktop
```

- Fix any problems reported by flutter doctor

```shell
flutter doctor
```

- Install LLVM

  - Based on your platform, install the LLVM using the [LLVM-16.0.0-win64(32)](https://github.com/llvm/llvm-project/releases/tag/llvmorg-16.0.0). Additionally, make sure to add it to the system path.

  ![install_llvm](../../../../.gitbook/assets/install_llvm.png)

- Install rust
  - Download `rustup.exe` from [https://win.rustup.rs/x86_64](https://win.rustup.rs/x86_64)
  - Call rustup.exe from powershell or cmd

```shell
.\rustup-init.exe --default-toolchain stable --default-host x86_64-pc-windows-msvc -y
```

It is a good idea to check your rustc version after this step, and compare it to the current supported one in AppFlowy. Run the command:

```
rustup --version
```

Look for `rustc 1.80.1` - You can find the supported version [here](https://github.com/AppFlowy-IO/AppFlowy/blob/0.5.6/.github/workflows/flutter_ci.yaml#L29).

In case you need to checkout/downgrade your version, you can replace the version number in this command:

```
rustup default 1.80.1
```

- Install cargo make

{% hint style="info" %}
You probably need to re-open your terminal to get the `cargo` command in your PATH
{% endhint %}

```shell
cd AppFlowy/frontend
```

```shell
cargo install --force cargo-make
```

- Install duckscript

```shell
cargo install --force duckscript_cli
```

- Add Powershell to the PATH

Add `C:\Windows\System32` to the PATH to prevent Powershell build commands crashing.

- Install openssl
  - Download `openssl_1.1.1n_win32_complete.zip` from [https://sockettools.com/kb/openssl-installation-packages-windows/](https://sockettools.com/kb/openssl-installation-packages-windows/)
  - Run installer and install Openssl where you want
  - Add `bin` folder to the PATH (ie: `G:\Compilation\OpenSSL\bin`)
  - Create a new User variable (using the same window as the PATH editor): Name it `OPENSSL_DIR` with same value as bin folder (ie `G:\Compilation\OpenSSL\bin`)

_Note:_ In cse the OpenSSL link resolves to a dead download, you can install OpenSSL from this [alternative source](https://slproweb.com/download/Win64OpenSSL-1_1_1w.exe). (From [https://slproweb.com/](https://slproweb.com/products/Win32OpenSSL.html))

- Install perl
  - Download Perl for Windows (called Strawberry perl) from [https://strawberryperl.com/](https://strawberryperl.com/) (choose x64 installer)
  - Run installer
  - Check Perl is installed with following command

```shell
perl --version
```

- Install Dart extension for Visual Studio Code
- Enable the Dart `protoc_plugin`

```shell
dart pub global activate protoc_plugin 21.1.2
```

- For Windows 11: Activate Developer Mode
  - Go to Settings > Privacy & Security > switch ON Developer Mode

## Step 3: Edit and run the application

\[VS Code]

1. Open the `frontend` folder located at xx/AppFlowy/frontend with VS Code.
2. Go to the Run and Debug tab and then click AF-desktop: Clean + Rebuild All for the first time running.

![img.png](../../../../.gitbook/assets/launch_appflowy.png)

If you encounter any issues, have a look at [Troubleshooting](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup/trouble-shotting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## Building in release mode

1. Go to the AppFlowy/frontend/ directory.
2. Run the following command to create the binary.

```bash
cargo make --profile production-windows-x86 appflowy
```

The scripts are located in the AppFlowy/frontend/Makefile.toml file.

The resulting binary file is located in `AppFlowy/frontend/appflowy/product/x.x.x/Windows/Release/AppFlowy/`.

If using a virtual machine

- Run Linux GUI application through x11 on windows (use MobaXterm) for instance:

`export DISPLAY=localhost:10`
