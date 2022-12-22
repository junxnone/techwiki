---
Title | Ubuntu thinclient_drives cannot access
-- | --
Created @ | `2019-08-14T01:30:26Z`
Last Modify @| `2022-12-22T07:43:50Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/124)

---
# thinclient_drives cannot access

> ubuntu上安装xrdp搭建远程桌面，后面远程桌面是可以了，但是用户目录下生出了一个thinclient_drives文件夹，无论是不是root都不能删除

```
ls: cannot access 'thinclient_drives': Transport endpoint is not connected

d?????????  ? ?    ?        ?            ? thinclient_drives/
```
## Solution

```
sudo umount thinclient_drives
```
