# Installing on Linux

AppFlowy currently does not have a formal Linux installation process. However, the application can quickly and easily be installed by the end user.

**Note:** AppFlowy requires glibc >= 2.32 however this version is not yet available in some common linux distributions. For the record, glibc 2.33 is available on Debian testing and Ubuntu 21.04:

**Note:**

* The following steps have been verified on the following Linux distributions:
  * [x] lubuntu 20.04 - X86\_64
  * [x] Arch Linux - X86\_64
  * [x] Ubuntu 20.04 - x86\_64
  
  Any Linux distribution not listed here has not been tested, and the following steps may not work. If you are trying to install AppFlowy on a Linux distribution not listed here, let us know how it went so that we can add it to the list or fix any bugs that may ocurr.

### Steps to install AppFlowy on Linux\*\*

1. Download the latest archive file from the [Releases](https://github.com/AppFlowy-IO/appflowy/releases) page.
2.  Extract the archive in a location of your choice (i.e. /opt/)

    **note:** Performing read/write operations in folders such as `/opt` may require root access. If a command fails due to missing permissions, try running it as the root user (this may be done by switching to the root user or using programs such as sudo and doas)
    **note:** The application will be extracted into a folder named AppFlowy

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

{% hint style="danger" %}
The current documentation may be out of sync with the development.&#x20;

* If your icon file is named `flowylogo.svg` **** please rename it to `app_flowy.svg`
* Your appflowy.desktop file should have the line `Icon=<installation_dir>/AppFlowy/app_flowy.svg`
{% endhint %}

Adding an application to Linux's system menu requires some extra steps. In the steps below we assume that you have extracted the archive file into the `/opt/` directory and that your present working directory is `/opt/AppFlowy`.

#### Add a Linux desktop file to your system

* Copy the temporary Linux desktop file to a usable Linux desktop file. Notice the underscore in app\_flowy.

```shell
cp appflowy.desktop.temp app_flowy.desktop
```

* Edit the `appflowy.desktop` file so that it points to the correct file.

```shell
Exec=[CHANGE_THIS]/AppFlowy/app_flowy
```

becomes (if you installed in /opt)

```shell
Exec=/opt/AppFlowy/app_flowy
```

* Move the desktop file so that Linux will pick it up

```shell
mv app_flowy.desktop ~/.local/share/applications/.
```

* Last but not least, copy the icon file so the system will pick it up.

```
cp app_flowy.svg ~/.icons/.
```
