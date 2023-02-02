# 🔁 Debugging in VS Code

Multiple launch configurations and tasks are defined for AppFlowy. These are used in the build process in order to generate needed files, clean up temporary files, and compile the source code.

## Launch Configurations

A launch configuration is what is used when you type `F5` or `Ctrl-F5`to launch the application.

You can select your preferred launch configuration by going to the `Run and Debug` tab in VS Code.

| Name                                   | Description                                                                                                                                                                                                                                                                                                                                                                           |
|----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AF-desktop: Build All                  | This will build the Rust and Dart code of AppFlowy.                                                                                                                                                                                                                                                                                                                                   |
| AF-desktop: Build All (rustlog: trace) |                                                                                                                                                                                                                                                                                                                                                                                       |
| AF-desktop: Build Dart Only            | This will only build the Dart code of AppFlowy. This should be your default when you are working on Flutter code.                                                                                                                                                                                                                                                                     |
| AF-desktop: Clean + Rebuild All        | <p>This task will:</p><ul><li>call the "<code>AF: Clean</code>" task,</li><li>rebuild all the generated Files (including freeze and language files)</li><li>rebuild the the Rust and Dart code of AppFlowy.</li></ul><p>This launch configuration is a convenience. A better way to do this would be to directly trigger the "<code>AF-desktop: Clean + Rebuild All</code>" task.</p> |
| AF: Debug Rust                         | This will show the `lldb` attach menu, in which you should select the `app_flowy` program to debug rust. Please note that this task is only valid when `app_flowy` is running and the `codellb` plugin for VS Code is installed.                                                                                                                                                      |

Launch configurations are defined in the `/frontend/.vscode/launch.json` file

## Tasks

Tasks are be launched manually (although you are free to keybind them locally). You can see a list of all tasks available by initiating the command palette (`Ctrl-Shift-P`) and then typing "run task".

![Inititiate the command palette with Ctrl-Shift-P](../../../.gitbook/assets/task\_pannel.png)

You can now type "AF:" to see a list of all AppFlowy provided tasks. Click on the desired task to trigger it.

![The AppFlowy tasks](../../../.gitbook/assets/task\_select.png)

{% hint style="info" %}
We recommend binding the `Alt-T key combination to the "Tasks: Run Task" command. This is done by initiating the command palette (Ctrl-Shift-P`) and then typing "`Open Keyboard Shortcuts`".
{% endhint %}

{% hint style="info" %}
Note that `Ctrl-Shift-B` will trigger the default build task. We have configured `AF: Code Gen` as the default build task.
{% endhint %}

In order to make them easy to identify, all AppFlowy defined tasks are prefixed with "AF: "

| Name                        | Description                                                                                                                                                                                                                                                                                                  | Depend On                                                                                                                                                                              |
|-----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| AF: Clean + Rebuild All     | This task will clean the code base, regenerate all needed files, and then build the Rust and Dart code of AppFlowy.                                                                                                                                                                                          | <ul><li>AF: Clean</li><li>AF: Flutter Pub</li><li>AF: Flutter Package Get</li><li>AF: Generate Language Files</li><li>AF: Generate Freezed Files</li><li>AF: build_flowy_sdk</li></ul> |
| AF: build_appflowy_core     | This task builds only the Rust code of AppFlowy. This is done by calling the `build_appflowy_core` script.                                                                                                                                                                                                   |                                                                                                                                                                                        |
| AF: Code Gen                | <p>This task will regenerate the required files to build AppFlowy. This includes the language translations, freezed files. It does not include the protobuf files.<br><br><strong>Note:</strong> This is the "default build task", this can be executed at any time by typing <code>Ctrl-Shift-B</code>.</p> | <ul><li>AF: Flutter Pub</li><li>AF: Flutter Package Get</li><li>AF: Generate Language Files</li><li>AF: Generate Freezed Files</li></ul>                                               |
| AF: Flutter Pub Get         | This will execute the `flutter pub get` command in the `/frontend/app_flowy` directory                                                                                                                                                                                                                       |                                                                                                                                                                                        |
| AF: Flutter Package Get     | This will execute the `flutter packages pub get` command in the `/frontend/app_flowy` directory                                                                                                                                                                                                              |                                                                                                                                                                                        |
| AF: Generate Freezed Files  | This will generate all the required freezed files.                                                                                                                                                                                                                                                           |                                                                                                                                                                                        |
| AF: Generate Language Files | This will generate all the required language translation files                                                                                                                                                                                                                                               |                                                                                                                                                                                        |
| AF: flutter build aar       | This will build AppFlowy in .aar format                                                                                                                                                                                                                                                                      |                                                                                                                                                                                        |

Tasks are defined in the `/frontend/.vscode/tasks.json` file.
