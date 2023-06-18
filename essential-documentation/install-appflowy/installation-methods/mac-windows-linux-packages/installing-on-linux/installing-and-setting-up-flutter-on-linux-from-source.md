# Flutter Installation Guide for Linux (Building from Source)


This guide provides step-by-step instructions to install and set up Flutter on Linux from source. It is primarily targeted at Debian-based distributions but should work for the majority of them.

Update your system by running the following command:

```shell 
sudo apt update
```
Install the necessary packages using the command:

```shell
sudo apt install curl file git unzip xz-utils zip libglu1-mesa clang cmake \ ninja-build pkg-config libgtk-3-dev
```
Optionally, you can choose to install cmake and ninja-build from source. This step is not recommended but provided for advanced users. You can download cmake from [here](https://cmake.org/download/) and ninja-build from [here](https://github.com/ninja-build/ninja/). Note that installing cmake is required to install ninja-build or Python.


Create a new folder for Flutter by running the following command:

```shell
mkdir projectfolder
``` 
Download the [latest Flutter SDK tarball file](https://docs.flutter.dev/development/tools/sdk/releases?tab=linux)

## Installation 

Change into the project folder you created earlier:

```shell
cd projectfolder
```
Extract the Flutter tarball file using the command:

```shell
tar xvf ~/Downloads/flutter_linux_*-stable.tar.xz
```
Add Flutter to your environment PATH by executing the following command:

```shell
export PATH="$PATH:[path-to-flutter-directory]/bin"
``` 
Optionally, you can add the PATH by opening the .bashrc file using the command:

```shell
nano ~/.bashrc
``` 
Add the PATH configuration there.

Replace [path-to-flutter-directory] in the above command with the actual path to the folder where you extracted the Flutter SDK. For example, if you extracted Flutter in a folder called projectfolder, the command will be:

```shell
export PATH="$PATH:~/projectfolder/flutter/bin"
```
**Save the file by pressing Ctrl+O and then Ctrl+X.**

### **Reload Terminal Session**
Reload your terminal session by either reopening the terminal or running the following command:

```shell
/bin/bash
```
Check if the Flutter PATH is correctly added to your shell by running:
```shell
echo $PATH
```
Once you have confirmed that Flutter is installed and the PATH is set, run the following command to check the Flutter version:
```shell
flutter --version
```

You should see a welcome screen along with the installed version of Flutter.

![flutter](https://user-images.githubusercontent.com/109571434/191872386-6694e72d-5bdb-4de4-ad59-86830f830f33.png)
