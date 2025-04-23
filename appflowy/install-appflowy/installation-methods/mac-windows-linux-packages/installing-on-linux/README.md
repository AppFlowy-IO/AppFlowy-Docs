# Installing on Linux

AppFlowy currently does not have a formal Linux installation process. However, the application can quickly and easily be installed by the end user.

**Note:** AppFlowy requires glibc >= 2.32 however this version is not yet available in some common linux distributions. For the record, glibc 2.33 is available on Debian testing and Ubuntu 21.04:

**Note:** The following steps have been verified on the following Linux distributions:

* [x] lubuntu 20.04 - x86\_64
* [x] Arch Linux - x86\_64
* [x] Ubuntu 20.04 - x86\_64
* [x] Linux Mint 20.3 x86\_64

Any Linux distribution not listed here has not been tested, and the following steps may not work. If you are trying to install AppFlowy on a Linux distribution not listed here, let us know how it went so that we can add it to the list or fix any bugs that may occur.

### Steps to install AppFlowy on Linux

1. Download the latest archive file from the [Releases](https://github.com/AppFlowy-IO/appflowy/releases) page.
2.  Extract the archive in a location of your choice (e.g. `/opt/`).

    **note:** Performing read/write operations in folders such as `/opt` may require root access. If a command fails due to missing permissions, try running it as the root user (this may be done by switching to the root user or using programs such as sudo and doas).

    **note:** The application will be extracted into a folder named AppFlowy.

```shell
tar -xzvf AppFlowy-*-linux-x86_64.tar.gz
```

3. Go to the AppFlowy directory.

```shell
cd AppFlowy
```

4. Run the application.

```shell
./AppFlowy
```

**NOTE:**
 _Please run `sudo chmod a+x /opt/AppFlowy/Appflowy` if the app doesn't launch on first try_

### Emoji Font Installation

AppFlowy will look for the **Noto Color Emoji** font on your system when trying to display emoji unicode characters. Please make sure that the font is configured so that emoji characters are displayed correctly.

**note:** Certain distributions (e.g. Fedora Linux) already have this set up by default. In that case, you can safely ignore this section.

1. Install the the font:
   * On Arch and Manjaro Linux, install `noto-fonts-emoji` using pacman.
   * On Ubuntu Linux and Linux Mint, install `fonts-noto-color-emoji` using apt.
2. Configure the font:
   * First, run `fc-cache -v` to reload the system font cache.
   * Then, create a file in `/etc/fonts/local.conf` with root privileges or `~/.config/fontconfig/fonts.conf` with the following content:

```
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
    <alias>
        <family>sans-serif</family>
        <prefer>
            <family>Sans</family>
            <family>Noto Color Emoji</family>
        </prefer>
    </alias>

    <alias>
        <family>serif</family>
        <prefer>
            <family>Serif</family>
            <family>Noto Color Emoji</family>
        </prefer>
    </alias>

    <alias>
        <family>monospace</family>
        <prefer>
            <family>Monospace</family>
            <family>Noto Color Emoji</family>
        </prefer>
    </alias>
</fontconfig>
```

3. Log out and log back in, or reboot to see your changes.

### Optional steps to add AppFlowy to your system menu

Adding an application to Linux's system menu requires some extra steps. In the steps below we assume that you have extracted the archive file contents into the `/opt/` directory and that your present working directory is `/opt/AppFlowy`.

#### Add a Linux desktop file to your system

* Rename the icon file.

```shell
sudo cp /opt/AppFlowy/data/flutter_assets/assets/images/flowy_logo.svg app_flowy.svg
```

* Copy the icon file so that the system will pick it up.

```
cp app_flowy.svg ~/.local/share/icons
```

* Create a desktop entry file in `~/.local/share/applications`

```shell
[Desktop Entry]
Name=AppFlowy
Comment=An Open Source Alternative to Notion
Icon=~/.local/share/icons/app_flowy.svg
Exec=/opt/AppFlowy/AppFlowy
Categories=Office
Type=Application
Terminal=false
```

* Restart after doing the above

**NOTE:**
 _Please run `sudo chmod a+x /opt/AppFlowy/Appflowy` if the app doesn't launch on first try_
