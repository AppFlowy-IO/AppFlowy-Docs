# ❓ Troubleshooting

## ❓ Troubleshooting

First of all, make sure the version of flutter and rust is the version specified in [here](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup)

### 1. Protobuf Generation Errors

1. Ensure the protoc-gen is installed

```shell
which protoc-gen-dart
```

2. Ensure the $HOME/.pub-cache/bin is shown in your $PATH.

```shell
echo $PATH
```

3. Ensure VS Code uses bash as the default terminal You can check out this [link](https://github.com/AppFlowy-IO/AppFlowy/issues/413) for more information.

### 2. Remove outdated files

AppFlowy uses `CodeGen` to generate some files that are ignored by git. So remove these files if there are some errors, warnings, and reference errors.

Here are the files are safe to remove

1. `AppFlowy/frontend/app_flowy/packages/flowy_sdk`
2. `AppFlowy/frontend/app_flowy/packages/appflowy_backend/lib/dispatch/dart_event`
3. `AppFlowy/frontend/app_flowy/packages/appflowy_backend/lib/protobuf`

### 3. Error: Not found: 'dart:ffi'

[issue #38](https://github.com/AppFlowy-IO/appflowy/issues/38)

Flutter Web / Android / iOS is not supported yet. Please switch to macOS or other supported devices.

### 4. How to use sql-data.json

Q: How to use sql-data.json

[https://github.com/AppFlowy-IO/appflowy/blob/main/backend/sqlx-data.json](https://github.com/AppFlowy-IO/appflowy/blob/main/backend/sqlx-data.json)

A: Check the offline mode section:

[https://docs.rs/sqlx/0.4.0-beta.1/sqlx/macro.query.html](https://docs.rs/sqlx/0.4.0-beta.1/sqlx/macro.query.html)

### 5. How to create a pull request

A: [https://opensource.com/article/19/7/create-pull-request-github](https://opensource.com/article/19/7/create-pull-request-github)

### 6. Permission denied

A: [https://stackoverflow.com/questions/2643502/git-how-to-solve-permission-denied-publickey-error-when-using-git](https://stackoverflow.com/questions/2643502/git-how-to-solve-permission-denied-publickey-error-when-using-git)

### 7. Failed to load dynamic library 'libdart\_ffi.so'

[issue #112](https://github.com/AppFlowy-IO/appflowy/issues/112) Q: Hello, when I run app with vs code\&android\&mac m1, it gave error:

ArgumentError (Invalid argument(s): Failed to load dynamic library 'libdart\_ffi.so': dlopen failed: library "libdart\_ffi.so" not found)

A: Are you trying to build for android? Appflowy only supports desktops as of now

[issue #191](https://github.com/AppFlowy-IO/appflowy/issues/191) Q. Unhandled Exception: Invalid argument(s): Failed to load dynamic library 'libdart\_ffi.so' on Ubuntu.

A: I append ubuntu 21.04 source.list's content to `/etc/apt/source.list`, and then upgrade `libc6`.

```shell
# Append the ubuntu 20.04's source.list to its tail.
$ sudo vim /etc/apt/source.list
$ sudo apt upgrade libc6
```

### 8. Build failed on Ubuntu 20.04

[issue #106](https://github.com/AppFlowy-IO/appflowy/issues/106)

Q: I follow the BUILD\_ON\_LINUX.md and failed on step 10 cargo make --profile development-linux-x86 flowy-sdk-dev

To Reproduce Just follow the BUILD\_ON\_LINUX.md

A: There are some issues in protobuf generation of appflowy on linux. If you skip that step, you can get it working. Protobuf has already been generated and is tracked in the repository. So it will work without regeneration as of now.

### 9. The document data could not be saved on Ubuntu

[issue #1306](https://github.com/AppFlowy-IO/AppFlowy/issues/1306)

### 10. Can't build development environment

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

### 15. Malicious software warning on install- MAC-OS

[issue #18](https://github.com/AppFlowy-IO/AppFlowy/issues/18) [issue #1313](https://github.com/AppFlowy-IO/AppFlowy/issues/1313)

### 16. Cannot run on Ubuntu 22.04

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

### 17. Run appyflowy in docker,but it not work: cannot open display: 0

**Q:**

Bug Description

xhost + docker run --rm -v $HOME/.Xauthority:/root/.Xauthority:rw -v /tmp/.X11-unix:/tmp/.X11-unix -v /dev/dri:/dev/dri -v /var/run/dbus/system\_bus\_socket:/var/run/dbus/system\_bus\_socket -v appflowy-data:/home/appflowy -e DISPLAY=${DISPLAY} appflowyio/appflowy\_client:main

(app\_flowy:1): Gtk-WARNING \*\*: 01:27:57.247: cannot open display: :0

**A:**

I add the param\
&#xNAN;**--network=host**

and it works

[issue: #2458](https://github.com/AppFlowy-IO/AppFlowy/issues/2458)

## 18. Can't run tests on windows "Failed to load dynamic library"

If you're trying to run tests on windows, but they're failing due to this message:

```
Invalid argument(s): Failed to load dynamic library
'C:\Users\mathias\AppFlowy\frontend\appflowy_flutter/.sandbox/dart_ffi.dll': error code 126
dart:ffi
open
   ...
```

Run this command from the frontend directory: `cargo make dart_unit_test`

_Optionally you can run this in bash instead of the above one, but you must be inside the appflowy\_flutter directory:_ `flutter test --dart-define=RUST_LOG=INFO -j, --concurrency=1 --coverage`
