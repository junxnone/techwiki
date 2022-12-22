---
Title | Desktop CentOS
-- | --
Created @ | `2018-11-29T04:59:44Z`
Last Modify @| `2022-12-22T08:03:17Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/175)

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
