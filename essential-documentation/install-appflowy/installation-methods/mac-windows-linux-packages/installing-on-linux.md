# Installing on Linux

AppFlowy currently does not have a formal Linux installation process. However, the application can quickly and easily be installed by the end user.

**Note:** AppFlowy requires glibc >= 2.32 however this version is not yet available in some common linux distributions. For the record, glibc 2.33 is available on Debian testing and Ubuntu 21.04:

**Note:**

* The following steps are verified on
  * [x] lubuntu 20.04 - X86\_64
  * [ ] ubuntu 20.04 - aarch64
  * [ ] redhat - X86\_64
  * [x] Arch Linux - X86\_64
  * [ ] Deepin - X86\_64
  * [ ] Raspberry Pi OS - aarch64

### Steps to install AppFlowy on Linux\*\*

1. Download the latest archive file from the [Releases](https://github.com/AppFlowy-IO/appflowy/releases) page.
2.  Extract the archive in a location of your choice (i.e. /opt/)

    **note :** The application will be extracted into a folder named AppFlowy

```shell
tar -xzvf AppFlowy-linux-x86.tar.gz
```

1. Go to the AppFlowy directory

```shell
cd AppFlowy
```

1. Run the application

```shell
./app_flowy
```

### Optional steps to add AppFlowy to your system menu

Adding an application to Linux's system menu requires some extra steps. In the steps below we assume that you have extracted the archive file into the `/opt/` directory and that your present working directory is `/opt/AppFlowy`.

#### Add a Linux desktop file to your system

* Copy the temporary Linux desktop file to a usable Linux desktop file.

```shell
cp appflowy.desktop.temp appflowy.desktop
```

* Edit the `appflowy.desktop` file so that it points to the correct files.

```shell
Icon=[CHANGE_THIS]/AppFlowy/flowy_logo.svg
Exec=[CHANGE_THIS]/AppFlowy/app_flowy
```

becomes

```shell
Icon=/opt/AppFlowy/flowy_logo.svg
Exec=/opt/AppFlowy/app_flowy
```

* Move the desktop file so that Linux will pick it up

```shell
mv appflowy.desktop ~/.local/share/applications/.
```
