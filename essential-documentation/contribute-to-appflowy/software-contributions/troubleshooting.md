# ❓ Troubleshooting

First of all, make sure the version of flutter and rust is the version specified in [here](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup)

## 1. Protobuf Generation Errors
1. Ensure the protoc-gen is installed
```shell
which protoc-gen-dart
```
2. Ensure the $HOME/.pub-cache/bin is shown in your $PATH.
```shell
echo $PATH
```

3. Ensure VS Code uses bash as the default terminal
You can check out this [link](https://github.com/AppFlowy-IO/AppFlowy/issues/413) for more information.

## 2. Remove outdated files
AppFlowy uses `CodeGen` to generate some files that are ignored by git. So remove these files if there are
some errors, warnings, and reference errors.

Here are the files are safe to remove
1. `AppFlowy/frontend/app_flowy/packages/flowy_sdk`
2. `AppFlowy/frontend/app_flowy/packages/appflowy_backend/lib/dispatch/dart_event`
3. `AppFlowy/frontend/app_flowy/packages/appflowy_backend/lib/protobuf`
