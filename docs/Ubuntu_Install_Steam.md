---
Title | Ubuntu Install Steam
-- | --
Create Date | `2021-09-19T10:19:39Z`
Update Date | `2021-09-19T10:19:39Z`
---
# Reference
- [How to install Steam on Ubuntu 20.04 Focal Fossa Linux](https://linuxconfig.org/how-to-install-steam-on-ubuntu-20-04-focal-fossa-linux)

# Install

- **N.B. Install 32bit  Nvidia GPU Driver**

```
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install wget gdebi-core libgl1-mesa-glx:i386
wget -O ~/steam.deb http://media.steampowered.com/client/installer/steam.deb
sudo gdebi ~/steam.deb
steam
```
