---
Title | Ubuntu Install Steam
-- | --
Created @ | `2021-03-02T12:27:32Z`
Last Modify @| `2022-12-21T08:42:38Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/4)

---
# Ubuntu Install Steam

## Reference
- [How to install Steam on Ubuntu 20.04 Focal Fossa Linux](https://linuxconfig.org/how-to-install-steam-on-ubuntu-20-04-focal-fossa-linux)

## Install Steam

- **N.B. Install 32bit  Nvidia GPU Driver**

```
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install wget gdebi-core libgl1-mesa-glx:i386
wget -O ~/steam.deb http://media.steampowered.com/client/installer/steam.deb
sudo gdebi ~/steam.deb
steam
```
