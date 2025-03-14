# 🌳 Flutter Setup

We have set up instructions for Linux, MacOS, and Windows.

{% hint style="warning" %}
Flutter version 3.27.4 is the version that AppFlowy is built and tested on. If you installed Flutter before, make sure the version matches AppFlowy's. And don't forget to run the following command to activate the protoc plugin.

```dart
dart pub global activate protoc_plugin 21.1.2
```

{% endhint %}

{% hint style="warning" %}
Rust version updates regularly (currently 1.80.1). If you have installed Rust before, make sure the stable version matches AppFlowy's (see `RUST_TOOLCHAIN` in `.github/workflows`).
{% endhint %}

[Building on Linux](building-on-linux.md)

[Building on MacOS](building-on-macos.md)

[Building on Windows](building-on-windows.md)

[Building on iOS](../../../../essential-documentation/contribute-to-appflowy/software-contributions/environment-setup/building-on-ios.md)
