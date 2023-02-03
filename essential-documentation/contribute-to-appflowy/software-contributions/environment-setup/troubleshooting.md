# ❓ Troubleshooting

First of all, make sure the version of flutter and rust is the version specified in [here](https://appflowy.gitbook.io/docs/essential-documentation/contribute-to-appflowy/software-contributions/environment-setup) 

## Protobuf Generation Errors
### 1.The protoc-gen-dart plugin error
Check your protoc-gen is installed or not.
```shell
which protoc-gen-dart
```

Because VS Code uses bash as the default terminal, ensure the $HOME/.pub-cache/bin is shown in your $PATH.
You can check out this [link](https://github.com/AppFlowy-IO/AppFlowy/issues/413) for more information.
