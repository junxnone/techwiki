---
Title | Ubuntu thinclient_drives cannot access
-- | --
Create Date | `2021-09-22T07:23:26Z`
Update Date | `2021-09-22T07:23:26Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/124)

---
> ubuntu上安装xrdp搭建远程桌面，后面远程桌面是可以了，但是用户目录下生出了一个thinclient_drives文件夹，无论是不是root都不能删除

```
ls: cannot access 'thinclient_drives': Transport endpoint is not connected

d?????????  ? ?    ?        ?            ? thinclient_drives/
```
# Solution

```
sudo umount thinclient_drives
```
