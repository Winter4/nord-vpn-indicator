# NordIndicator

NordIndicator is a Python script that lets you connect, disconnect and check your NordVPN connection status and settings from a simple GNU/Linux tray app indicator. It integrates with your system so it autostarts with it, and you can also launch it from your OS app menu.

## Features
* Check your connection status, server, location, IP and current settings
* Fast connection and connect to a Switzerland/United States/P2P server
* Disconnect
* Enable/Disable settings by clicking the menu items: technology, cybersec, firewall, killswitch, autoconnect, dns...

## Pre-requirements
- [NordVPN CLI for GNU/Linux](https://support.nordvpn.com/es/Preguntas-frecuentes/Tutoriales-de-configuraci%c3%b3n/1636892662/Instalar-y-utilizar-NordVPN-en-Debian-Ubuntu-Raspberry-Pi-Elementary-OS-y-Linux-Mint.htm)
- `python3-gi` package
- [AppIndicator](https://debian.pkgs.org/10/debian-main-amd64/gir1.2-appindicator3-0.1_0.4.92-7_amd64.deb.html) library (depending on your **Linux distribution**, you may have to install it manually)

  - If the library is not installed, you will face the error; something like that:

    ```
    $ user@user-pc:~/NordIndicator$ python3 NordIndicator.py install

    Traceback (most recent call last):
    File "/home/USERNAME/NordIndicator/NordIndicator.py", line 9, in <module> require_version('AppIndicator3', '0.1')
    File "/usr/lib/python3/dist-packages/gi/__init__.py", line 126, in require_version
    raise ValueError('Namespace %s not available' % namespace)
    ValueError: Namespace AppIndicator3 not available
    ```

    This one was reproduced on **Ubuntu 22.04**. To fix that, install the package (_Ubuntu example_):

    ```
    sudo apt install gir1.2-appindicator3-0.1
    ```

## Notes
* NordIndicator has been only tested with elementary OS 5.1 (Ubuntu 18.04 based) but due to its simplicity making it work on those distros where it doesn't shouldn't be more than editing a couple of lines of code. The same applies to other VPN providers.

* The installation is made at user-level, so everything happens within your  home directory and no sudo permissions are needed.

## Installation
* NordIndicator will be launched just after installation. It will also auto-start on system boot.
* ```python3 NordIndicator.py install```

## Optional Configuration
You can choose between two countries for quick connection in the menu. By default, it will be Switzerland and United States. To edit these defaults :
* After installation, go to ```~/.config/NordIndicator```. You can then edit ``config.py`` by replacing `country1` and/or `country2`. Be careful not to make any typo or the quick connect option won't work. You can find a list of availible country by typing ``nordvpn countries`` in a terminal.

## Uninstallation
* NordIndicator running processes will be killed before uninstallation.
* ```python3 NordIndicator.py uninstall```

## Upgrade
* NordIndicator autoupgrades on every run, but you can force an upgrade.
* ```python3 NordIndicator.py upgrade```

## Snapshots
![Imgur](https://i.imgur.com/3LQ2kz9.png)

![Imgur](https://i.imgur.com/oGW1Fie.png)
