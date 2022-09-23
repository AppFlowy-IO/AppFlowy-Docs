# Installing & Setting up Flutter on Linux from Source

This guide will show you how to install and get Flutter working to install AppFlowy. This **should** work for majority on Debian Based Distros. 

Begin by running a system update with 
```shell 
sudo apt update
```
Then install the neccessary packages. 

```shell
sudo apt install curl file git unzip xz-utils zip libglu1-mesa clang cmake \ ninja-build pkg-config libgtk-3-dev
```
Personally, I reccomend installing cmake & ninja-build from source. This is completely optional and not reccomended. [cmake download](https://cmake.org/download/)  [ninja-build](https://github.com/ninja-build/ninja) <- cmake is required to install ninja-build OR python.

Create a new Folder for Flutter 
```shell
mkdir projectfolder
``` 
Then install the [latest Flutter SDK tarball file](https://docs.flutter.dev/development/tools/sdk/releases?tab=linux)

## Installition 

cd into the project folder you created earlier.

```shell
cd projectfolder
```
Extract the Flutter file

```shell
tar xvf ~/Downloads/flutter_linux_*-stable.tar.xz
```
Add Flutter to your environment PATH

```shell
export PATH="$PATH:[path-to-flutter-directory]/bin"
``` 
Optionally, you can also run 

```shell
nano ~/.bashrc
``` 
and add the PATh there. 

Replace [path-to-flutter-directory]  in the above command with the actual path of the folder where you have extracted the Flutter.

For example, here we have created a folder called projectfolder and under it, we have extracted the folder. Hence the above command in our case will be:

```shell
export PATH="$PATH:~/projectfolder/flutter/bin"
```
**Save** the file by pressing **Ctrl+O** and then **Ctr+X**.

### **Reload Terminal Session**
You can exit the terminal and reopen, or run
```shell
/bin/bash
```
Check if the Flutter PATH is added into your shell.
```shell
echo $PATH
```
Once you've confirmed that flutter is installed and added to PATh, run 
```shell
flutter --version
```

You should see a screen that welcomes you and the version.

![flutter](https://user-images.githubusercontent.com/109571434/191872386-6694e72d-5bdb-4de4-ad59-86830f830f33.png)
