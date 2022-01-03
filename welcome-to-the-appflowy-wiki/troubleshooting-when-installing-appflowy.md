# Troubleshooting when installing AppFlowy

### 1. Error: Not found: 'dart:ffi'

[issue #38](https://github.com/AppFlowy-IO/appflowy/issues/38)

Flutter Web / Android / iOS is not supported yet. Please switch to macOS or other supported devices.

### 2. Package do not exist in  git@github.com:appflowy/flutter-quill.git for flutter-quill

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

### 7. Build failed on Ubuntu 20.04

[issue #106](https://github.com/AppFlowy-IO/appflowy/issues/106)

Q: I follow the BUILD\_ON\_LINUX.md and failed on step 10 cargo make --profile development-linux-x86 flowy-sdk-dev

To Reproduce Just follow the BUILD\_ON\_LINUX.md

A: There are some issues in protobuf generation of appflowy on linux. If you skip that step, you can get it working. Protobuf has already been generated and is tracked in the repository. So it will work without regeneration as of now.
