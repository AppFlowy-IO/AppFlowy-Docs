# FlowySDK (WIP)

FlowySDK works as the AppFlowy application Back-end. It will be initialized before the application launch. Check out the initialization sequence diagram shown below.

![file : flowy_sdk.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/FlowySDK-Initialization.svg)

1. FlowyRunner will get called when the entry point, the `main` function, got called.
2. FlowyRunner call `initialize` function on each task that registers as a LaunchTask one by one.
3. `InitRustSDKTask` calls the init function and passes the working directory into FlowySDK.
   ```dart
    getIt<FlowySDK>().init(directory)
    ``` 
   The directory is different according to the IntegrationMode, which means running AppFlowy on
   developing mode will not alter the data on release mode. 
   1. IntegrationMode.release
   ```dart
    Directory documentsDir = await getApplicationDocumentsDirectory();
    final directory = Directory('${documentsDir.path}/flowy')
    ``` 
   2. IntegrationMode.develop
   ```dart
    Directory documentsDir = await getApplicationDocumentsDirectory();
    final directory = Directory('${documentsDir.path}/flowy_dev')
    ``` 
   3. IntegrationMode.test
   ```dart
    final directory = Directory("${Directory.current.path}/.sandbox")
    ```
5. `InitAppWidgetTask` initialize the `ApplicationWidget` and call `runApp` function.
6. `InitPlatformServiceTask` start the `NetworkListener`.




