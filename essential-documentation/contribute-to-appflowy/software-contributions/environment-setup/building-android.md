# 🤖 Building Android

## Step 1: Get the tools

You need the following tools in order to get started

* Get the right android NDK for your system [supported ndk](https://github.com/android/ndk/wiki/Unsupported-Downloads#r24)
* Android NDK r24 has been tested and currently works.
* You need to extract the archive and add the directory to the path.
  * Windows:
  `export ANDROID_NDK_HOME=C:\ndk\24.0.8215888`
  * Linux:
  `ANDROID_NDK_HOME=$HOME/ndk/24.0.8215888`
  * MacOS:
  `export ANDROID_NDK_HOME=$HOME/ndk/24.0.821588`
* You then need to install cargo-ndk using `cargo install cargo-ndk`

## Step 2: Compile the Rust SDK

You can compile the rust SDK with the command `cargo make --profile development-android appflowy-core-dev-android`.
There is also an option of using the vscode task `AF: Build Appflowy Core_for_android`

## Step 3: Run the App

After building the SDK you can run the app from VSCode ;)

