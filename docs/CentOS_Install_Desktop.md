---
Title | CentOS Install Desktop
-- | --
Create Date | `2021-10-12T15:26:26Z`
Update Date | `2021-10-12T15:26:26Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/175)

---
# Reference
- [How to install Desktop Environments on CentOS 7?](https://unix.stackexchange.com/questions/181503/how-to-install-desktop-environments-on-centos-7)

# Brief
- Desktop
  - [Gnome](##Gnome)
  - [KDE](##KDE)


## Gnome
### Install

```
 yum -y groups install "GNOME Desktop" 
```

### Start

```
startx
```

## KDE
### Install

```
 yum -y groups install "KDE Plasma Workspaces" 
```

### Start

```
echo "exec startkde" >> ~/.xinitrc
startx
```
