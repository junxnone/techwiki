---
Title | Ubuntu upgrade
-- | --
Create Date | `2021-09-22T05:10:58Z`
Update Date | `2021-09-22T05:10:58Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/89)

---

# Brief
- 升级 `Ubuntu 16.04` 到 `18.04`

## Steps
- **1 先更新当前的16.04**
```
sudo apt update && sudo apt dist-upgrade && sudo apt autoremove
```

- **2  升级至 lts**

```
sudo do-release-upgrade -d
```
> 时间比较长 ，如果系统可以重装还是重装快

--- 

**如果 python 链接为 python3,则会出现如下报错，重新链接回 python2.7 即可**
```
Your python3 install is corrupted. Please fix the '/usr/bin/python3' symlink.
```
