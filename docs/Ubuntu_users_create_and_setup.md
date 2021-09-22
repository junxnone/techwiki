---
Title | Ubuntu users create and setup
-- | --
Create Date | `2021-09-22T05:51:53Z`
Update Date | `2021-09-22T05:51:53Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/94)

---
# Reference
- [Ubuntu 16.04下添加新用户](https://www.linuxidc.com/Linux/2017-04/142690.htm)

# Brief


## UseCase

Usecase | cmd
-- | --
Create new user with home folder | `sudo useradd  -r -m  -s /bin/bash gpu` <br>`-m 创建用户目录在 /home/gpu`
指定目录为用户名主目录 | `usermod -d /home/xx/gpu gpu`
添加用户到某个group | `sudo usermod -aG guestgroup username`


## 为用户添加 `root` 权限

```
chmod +w /etc/sudoers 
vi /etc/sudoers 
```
添加如下内容：
```
gpu ALL=(ALL:ALL) ALL
```

## Issues 

- 无 `.bashrc`
  - 从其他用户 copy `.bashrc`/`.profile` 到 当前用户，重新登录即可
