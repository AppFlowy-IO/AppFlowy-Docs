# 🍎 Building on MacOS

**Note:**

* If you encounter any issues, have a look at [Troubleshooting](https://github.com/AppFlowy-IO/appflowy/wiki/Troubleshooting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## **Step 1: Get the source code**

{% hint style="warning" %}
You should fork the code instead if you wish to submit code to AppFlowy. You'll find information on that in [setting-up-your-repositories.md](../submitting-code/setting-up-your-repositories.md "mention")
{% endhint %}

```shell
git clone https://github.com/AppFlowy-IO/appflowy.git
```

## **Step 2: Install Flutter**

{% hint style="info" %}
Skip this if flutter is already installed on your system.
{% endhint %}

* Follow the instructions [here](https://flutter.dev/docs/get-started/install) to install Flutter.
  * It will ask you to run `flutter doctor` to check any dependencies you need to install to complete the setup.&#x20;
    * It is not necessary to install Android toolchain and Android studio to run AppFlowy.
    * However, CocoaPods and VS Code are required.
* Make sure you also install the [Flutter](https://marketplace.visualstudio.com/items?itemName=Dart-Code.flutter) & [Dart](https://marketplace.visualstudio.com/items?itemName=Dart-Code.dart-code) extensions in VS Code.

## **Step 3: Install your build environment**

* Run the setup script from the base directory
  * It will guide you through to install Rust, which is required by AppFlowy

```bash
./frontend/scripts/install_dev_env/install_ios.sh
```

> FYI, AppFlowy uses [https://github.com/sagiegurari/cargo-make](https://github.com/sagiegurari/cargo-make) to construct the build scripts. It is important that you add (dart) `pub` to $PATH, otherwise VS Code may error out. Add the following to your `.bashrc` or `.zshrc` in `$HOME`:
>
> ```
> export PATH="$PATH":"$HOME/.pub-cache/bin"
> ```
>
> Make sure to restart your terminal and VS Code

## **Step 4: Edit and run the application**

1. Open the `frontend` folder located at xx/AppFlowy/frontend with VS Code. It is important _not_ to open the root folder, as that will not give access to the appropriate debug commands.
2. Check the device selection: ![device](../../../../.gitbook/assets/vscode-ios-simulator.png)
3. Go to the Run and Debug tab and then click AF-iOS-Simulator: Clean + Rebuild All for the first time running.

![img.png](../../../../.gitbook/assets/launch-appflowy-ios.png)

> Or, you can select the real device and click AF-iOS: Clean + Rebuild All.

If you encounter any issues, have a look at [Troubleshooting](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup/trouble-shotting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## **Optional: Run the Application on terminal**

```bash
cd frontend/
cargo make --profile development-ios-arm64(-sim) appflowy-core-dev-ios # use development-ios-arm64-sim if running on simulator.
cd appflowy_flutter
sh scripts/code_generation/generate.sh
flutter run
```