# 🪟 Building on Windows

**Note:**

* The following steps are verified on
  * [x] Windows 10 X86\_64
  * [ ] Windows 10 arm64
  * [ ] Windows 11 X86\_64
  * [ ] Windows 11 arm64

**Note:**

* Both Windows `cmd` and `powershell` can be used for running commands.
* If you encounter any issues, please have a look at [Troubleshooting](https://github.com/AppFlowy-IO/appflowy/wiki/Troubleshooting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

##

## Step 1: Get the source code

{% hint style="info" %}
You should fork the code instead if you wish to submit patches. You'll find information on that in [Submitting your first Pull Request](../submitting-your-first-pull-request.md)
{% endhint %}

```shell
git clone https://github.com/AppFlowy-IO/appflowy.git
```

## Step 2: Install your build environment

* Install Visual Studio 2022 build tools. Download from [https://visualstudio.microsoft.com/downloads/](https://visualstudio.microsoft.com/downloads/)
  * In section "All Downloads" => "Tools for Visual Studio 2022" => "Build Tools for Visual Studio 2022".
  * Launch `vs_BuildTools.exe` to install.
* Install vcpkg according to [this page](https://github.com/microsoft/vcpkg#quick-start-windows). Make sure to add vcpkg installation folder to your PATH environment variable.
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
.\rustup-init.exe --default-toolchain nightly --default-host x86_64-pc-windows-msvc -y
```

* Install cargo make

{% hint style="info" %}
You probably need to re-open your terminal to get the `cargo` command in your PATH
{% endhint %}

```shell
cd appflowy/frontend
```

```shell
cargo install --force cargo-make
```

* Install duckscript

```shell
cargo install --force duckscript_cli
```

## Step 3: Build AppFlowy (Flutter GUI application)

* Check prerequisites

```shell
cargo make flowy_dev
```

* \[Optional] Generate protobuf for dart (if you wish to modify the shared-lib's entities)

```shell
# Need to download protoc tools and add it's bin folder into PATH env var.
# Download protoc from https://github.com/protocolbuffers/protobuf/releases. The latest one is protoc-3.19.1-win64.zip
cargo make -p development-windows pb
```

* \[Optional] Build flowy-sdk (dart-ffi), step 10 covers this step

{% tabs %}
{% tab title="Development" %}
```
cargo make --profile development-windows-x86 flowy-sdk-dev
```
{% endtab %}

{% tab title="Production" %}
```
cargo make --profile production-windows-x86 flowy-sdk-release
```
{% endtab %}
{% endtabs %}

* Build AppFlowy

{% tabs %}
{% tab title="Development" %}
```
cargo make -p development-windows-x86 appflowy-windows-dev
```
{% endtab %}

{% tab title="Production" %}
```
cargo make -p production-windows-x86 appflowy-windows
```
{% endtab %}
{% endtabs %}

## Step 4: Run the application

```bash
cd app_flowy/product/0.0.2/windows/Debug/AppFlowy
```

```shell
./app_flowy
```

* If using a virtual machine
  * Run Linux GUI application through x11 on windows (use MobaXterm) for instance:

`export DISPLAY=localhost:10`

## Step 5: Edit and run the application

\[VS Code]

1. Open the app\_flowy folder located at xx/appflowy/frontend/app\_flowy with VS Code.
2. Go to the Run and Debug tab and then click the run button.

![](<../../../../.gitbook/assets/image (1) (1).png>)

## Building in release mode

1. Go to the appflowy/frontend/ directory.
2. Run the following command to create the binary.

```bash
cargo make --profile production-windows-x86 appflowy
```

The scripts are located in the appflowy/frontend/Makefile.toml file.

The resulting binary file is located in `appflowy/frontend/app_flowy/product/x.x.x/Windows/Release/AppFlowy/`.
