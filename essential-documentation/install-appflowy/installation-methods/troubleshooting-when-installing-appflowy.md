---
description: >-
  This page documents a collection of resources to help you troubleshoot an
  AppFlowy installation.
---

# Troubleshooting

### 1. Error: Not found: 'dart:ffi'

[issue #38](https://github.com/AppFlowy-IO/appflowy/issues/38)

Flutter Web / Android / iOS is not supported yet. Please switch to macOS or other supported devices.

### 2. Package do not exist in git@github.com:appflowy/flutter-quill.git for flutter-quill

[issue #61](https://github.com/AppFlowy-IO/appflowy/issues/61)

Q: When try to get package for appflowy in pubspec.yaml. it says i dont have access or package does not exist in [git@github.com](mailto:git@github.com):appflowy/flutter-quill.git for flutter-quill.

Steps to reproduce the behavior:

1. get packages from pubspec.yaml
2. it shows error says does not have access to package

A:

Check this : [https://stackoverflow.com/questions/2643502/git-how-to-solve-permission-denied-publickey-error-when-using-git](https://stackoverflow.com/questions/2643502/git-how-to-solve-permission-denied-publickey-error-when-using-git)

### 3. How to use sql-data.json

Q: How to use sql-data.json

[https://github.com/AppFlowy-IO/appflowy/blob/main/backend/sqlx-data.json](https://github.com/AppFlowy-IO/appflowy/blob/main/backend/sqlx-data.json)

A: Check the offline mode section:

[https://docs.rs/sqlx/0.4.0-beta.1/sqlx/macro.query.html](https://docs.rs/sqlx/0.4.0-beta.1/sqlx/macro.query.html)

### 4. How to create a pull request

A: [https://opensource.com/article/19/7/create-pull-request-github](https://opensource.com/article/19/7/create-pull-request-github)

### 5. Permission denied

A: [https://stackoverflow.com/questions/2643502/git-how-to-solve-permission-denied-publickey-error-when-using-git](https://stackoverflow.com/questions/2643502/git-how-to-solve-permission-denied-publickey-error-when-using-git)

### 6. Failed to load dynamic library 'libdart\_ffi.so'

[issue #112](https://github.com/AppFlowy-IO/appflowy/issues/112)

Q: Hello, when I run app with vs code\&android\&mac m1, it gave error:

ArgumentError (Invalid argument(s): Failed to load dynamic library 'libdart\_ffi.so': dlopen failed: library "libdart\_ffi.so" not found)

A: Are you trying to build for android? Appflowy only supports desktops as of now

[issue #191](https://github.com/AppFlowy-IO/appflowy/issues/191)

Q. Unhandled Exception: Invalid argument(s): Failed to load dynamic library 'libdart\_ffi.so' on Ubuntu.

A: I append ubuntu 21.04 source.list's content to `/etc/apt/source.list`, and then upgrade `libc6`.

```shell
# Append the ubuntu 20.04's source.list to its tail.
$ sudo vim /etc/apt/source.list
$ sudo apt upgrade libc6
```

### 7. Build failed on Ubuntu 20.04

[issue #106](https://github.com/AppFlowy-IO/appflowy/issues/106)

Q: I follow the BUILD\_ON\_LINUX.md and failed on step 10 cargo make --profile development-linux-x86 flowy-sdk-dev

To Reproduce Just follow the BUILD\_ON\_LINUX.md

A: There are some issues in protobuf generation of appflowy on linux. If you skip that step, you can get it working. Protobuf has already been generated and is tracked in the repository. So it will work without regeneration as of now.

### 8. The document data could not be saved on Ubuntu

[issue #1306](https://github.com/AppFlowy-IO/AppFlowy/issues/1306)

### 9. Can't build development environment

Q. While executing install\_linux.sh script at compiling diesel\_cli i'm getting following error:

```
error: linking with `cc` failed: exit status: 1
...
= note: /usr/bin/ld: cannot find -lsqlite3
          collect2: error: ld returned 1 exit status


error: could not compile `diesel_cli` due to previous error
error: failed to compile `diesel_cli v2.0.0`, intermediate artifacts can be found at `/tmp/cargo-install4xWPP3`
```

[issue #1076](https://github.com/AppFlowy-IO/AppFlowy/issues/1076)

### 10. App don't run in Fedora 36

```
[ERROR:flutter/lib/ui/ui_dart_state.cc(198)] Unhandled Exception: Invalid argument(s): Failed to load dynamic library 'libdart_ffi.so': libssl.so.1.1: No file
#0 _open (dart:ffi-patch/ffi_dynamic_library_patch.dart:12)
#1 new DynamicLibrary.open (dart:ffi-patch/ffi_dynamic_library_patch.dart:23)
#2 _open (package:flowy_sdk/ffi.dart:23)
#3 _dl (package:flowy_sdk/ffi.dart:10)
#4 _set_stream_port (package:flowy_sdk/ffi.dart)
#5 set_stream_port (package:flowy_sdk/ffi.dart)
#6 FlowySDK.init (package:flowy_sdk/flowy_sdk.dart:32)
#7 InitRustSDKTask.initialize. (package:app_flowy/startup/tasks/rust_sdk.dart:13)
#8 InitRustSDKTask.initialize. (package:app_flowy/startup/tasks/rust_sdk.dart:12)
#9 _rootRunUnary (dart:async/zone.dart:1434)
#10 InitRustSDKTask.initialize (package:app_flowy/startup/tasks/rust_sdk.dart:12)
#11 AppLauncher.launch (package:app_flowy/startup/startup.dart:99)
```

[issue #702](https://github.com/AppFlowy-IO/AppFlowy/issues/742)

### 11. Docker Hub (app\_flowy:1): Gtk-WARNING \*\*: 10:44:25.079: cannot open display

[issue #389](https://github.com/AppFlowy-IO/AppFlowy/issues/389)

### 12. Failed to start Flutter renderer: Unable to create a GL context

```
⋊> ./app_flowy
** (app_flowy:21547): WARNING **: 03:05:10.061: Failed to start Flutter renderer: Unable to create a GL context
** (app_flowy:21547): WARNING **: 03:05:12.733: Unable to retrieve framework response: No engine to send to
```

[issue #295](https://github.com/AppFlowy-IO/AppFlowy/issues/295)

### 13. Cannot run on Macbook M1 chip

\[issue #255] (https://github.com/AppFlowy-IO/AppFlowy/issues/255)

### 14. Windows Build Failed

[issue #210](https://github.com/AppFlowy-IO/AppFlowy/issues/210)

### 15. Linux failing on cargo make flowy\_dev pre-request step

[issue #53](https://github.com/AppFlowy-IO/AppFlowy/issues/52)

### 16. Malicious software warning on install- MAC-OS

[issue #18](https://github.com/AppFlowy-IO/AppFlowy/issues/18) [issue #1313](https://github.com/AppFlowy-IO/AppFlowy/issues/1313)

\###17. Cannot run on Ubuntu 22.04

```
[ERROR:flutter/lib/ui/ui_dart_state.cc(198)] Unhandled Exception: Invalid argument(s): Failed to load dynamic library 'libdart_ffi.so': libssl.so.1.1: cannot open shared object file: No such file or directory
#0      _open (dart:ffi-patch/ffi_dynamic_library_patch.dart:12)
#1      new DynamicLibrary.open (dart:ffi-patch/ffi_dynamic_library_patch.dart:23)
#2      _open (package:flowy_sdk/ffi.dart:23)
#3      _dl (package:flowy_sdk/ffi.dart:10)
#4      _set_stream_port (package:flowy_sdk/ffi.dart)
#5      set_stream_port (package:flowy_sdk/ffi.dart)
#6      FlowySDK.init (package:flowy_sdk/flowy_sdk.dart:32)
#7      InitRustSDKTask.initialize.<anonymous closure> (package:app_flowy/startup/tasks/rust_sdk.dart:13)
#8      InitRustSDKTask.initialize.<anonymous closure> (package:app_flowy/startup/tasks/rust_sdk.dart:12)
#9      _rootRunUnary (dart:async/zone.dart:1434)
<asynchronous suspension>
#10     InitRustSDKTask.initialize (package:app_flowy/startup/tasks/rust_sdk.dart:12)
<asynchronous suspension>
#11     AppLauncher.launch (package:app_flowy/startup/startup.dart:99)
<asynchronous suspension>
```

[issue #566](https://github.com/AppFlowy-IO/AppFlowy/issues/566)

### 18. Unable to generate protobuf files due to permission issue in Mac.

While running `clean+rebuild all` command we might get an error due to a permission issue in Mac.

ie, the script present inside the `./scripts/build_sdk.sh` might be failing. You can fix it by running the script with sudo permission.

```
sudo FLOWY_DEV_ENV=macOS sh ./scripts/build_sdk.sh
```
