# 🍎 Building on MacOS



**Note:**

* If you encounter any issues, have a look at [Troubleshooting](https://github.com/AppFlowy-IO/appflowy/wiki/Troubleshooting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).

## **Step 1: Get the source code**

{% hint style="warning" %}
You should fork the code instead if you wish to submit patches. You'll find information on that in **** [setting-up-your-repositories.md](../submitting-code/setting-up-your-repositories.md "mention")****
{% endhint %}

```shell
git clone https://github.com/AppFlowy-IO/appflowy.git
```

## **Step 2: Install Rust and Cargo**

{% hint style="info" %}
Skip install\_rust or install\_cargo\_make if you already installed it.
{% endhint %}

```shell
cd appflowy/frontend
```

```shell
make flowy_dev
```


> FYI, AppFlowy uses [https://github.com/sagiegurari/cargo-make](https://github.com/sagiegurari/cargo-make) to construct the build scripts

## **Step 3: Install Flutter**

* Follow the instructions [here](https://flutter.dev/docs/get-started/install) to install Flutter.
* As AppFlowy uses the `stable` channel, you need to switch the channel.

```shell
flutter channel stable
```

* Enable the specified platform first if you don't enable it before and then select the desktop device.

```shell
flutter config --enable-macos-desktop
```

## **Step 4: Edit and run the application**

* Open the `app_flowy` folder located at xx/appflowy/frontend with VS Code.
* Go to the Run and Debug tab and then click the run button.

![](../../../../.gitbook/assets/image.png)

* Please also check the device selection, as of now AppFlowy only supports Desktop: ![device](https://user-images.githubusercontent.com/86001920/144546864-cebbf0c0-4eef-424e-93c7-e1e6b3a59669.png)

## Building in release mode

1. Go to the appflowy/frontend/ directory.
2. Run the following command to build the binary depending on your architecture.

{% tabs %}
{% tab title="x86" %}
```shell
cargo make --profile production-mac-x86 appflowy
```
{% endtab %}

{% tab title="aarch64" %}
```shell
cargo make --profile production-mac-aarch64 appflowy
```
{% endtab %}
{% endtabs %}

The scripts are located in the appflowy/frontend/Makefile.toml file.

The resulting binary file is located in `appflowy/frontend/app_flowy/product/x.x.x/[OS]/Release/AppFlowy/`.

* If you encounter any issues, have a look at [Troubleshooting](https://github.com/AppFlowy-IO/appflowy/wiki/Troubleshooting) first. If your issue is not included in the page, please create an [issue](https://github.com/AppFlowy-IO/appflowy/issues/new/choose) or ask on [Discord](https://discord.gg/9Q2xaN37tV).
