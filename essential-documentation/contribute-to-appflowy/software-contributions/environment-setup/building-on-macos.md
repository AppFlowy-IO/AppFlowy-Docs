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

## **Step 3: Install your build environment**

* Run the setup script from the base directory

```bash
./frontend/scripts/install_dev_env/install_macos.sh
```

> FYI, AppFlowy uses [https://github.com/sagiegurari/cargo-make](https://github.com/sagiegurari/cargo-make) to construct the build scripts

## **Step 4: Edit and run the application**

1. Open the `frontend` folder located at xx/AppFlowy/frontend with VS Code.
2. Go to the Run and Debug tab and then click AF: Clean + Rebuild All for the first time running.

![img.png](../../../../.gitbook/assets/launch\_appflowy.png)

* Please also check the device selection, as of now AppFlowy only supports Desktop: ![device](https://user-images.githubusercontent.com/86001920/144546864-cebbf0c0-4eef-424e-93c7-e1e6b3a59669.png)

If you encounter any issues, have a look at [Troubleshooting](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup/trouble-shotting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## Building in release mode

1. Go to the AppFlowy/frontend/ directory.
2. Run the following command to build the binary depending on your architecture.

{% tabs %}
{% tab title="x86" %}
```shell
cargo make --profile production-mac-x86 appflowy
```
{% endtab %}

{% tab title="arm64" %}
```shell
cargo make --profile production-mac-arm64 appflowy
```
{% endtab %}
{% endtabs %}

The scripts are located in the AppFlowy/frontend/Makefile.toml file.

The resulting binary file is located in `AppFlowy/frontend/app_flowy/product/x.x.x/[OS]/Release/AppFlowy/`.
