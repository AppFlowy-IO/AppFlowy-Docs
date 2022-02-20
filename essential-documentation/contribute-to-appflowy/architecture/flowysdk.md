# FlowySDK (WIP)

FlowySDK works as the AppFlowy application Back-end. It will be initialized before the application launch. Check out the initialization sequence diagram shown below.

![file : flowy_sdk.plantuml](https://raw.githubusercontent.com/AppFlowy-IO/docs/main/uml/output/FlowySDK-Initialization.svg)

1. FlowyRunner will get called when the entry point, the `main` function, got called.
2. FlowyRunner call `initialize` function on each task that registers as a LaunchTask one by one.
3. `InitRustSDKTask` calls the init function and passes the working directory into FlowySDK.
   ```dart
    getIt<FlowySDK>().init(directory)
    ``` 
4. `InitAppWidgetTask` initialize the `ApplicationWidget` and call `runApp` function.
5. `InitPlatformServiceTask` start the `NetworkListener`.




