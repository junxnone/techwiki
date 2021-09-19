---
Title | Ubuntu auto mount disk
-- | --
Create Date | `2021-09-19T14:52:03Z`
Update Date | `2021-09-19T14:52:03Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/13)

---
# 使用 fdisk 对第二硬盘分区
```
sudo fdisk /dev/sdb
```
# 备份 /etc/fstab
```
sudo cp /etc/fstab /etc/fstab.bk
```
# 查看uuid
```
ll /dev/disk/by-uuid/
```
```
total 0
drwxr-xr-x 2 root root  80 Dec  2 17:25 ./
drwxr-xr-x 6 root root 120 Dec  2 17:22 ../
lrwxrwxrwx 1 root root  10 Dec  2 17:23 982f2bda-f4a8-11e8-xxxx-x0946667160e -> ../../sda2
lrwxrwxrwx 1 root root  10 Dec  2 17:25 c92d59c3-c9d0-4382-xxxx-x44e4e900d94 -> ../../sdb1
```
# 更改fstab
添加如下内容
```
# <file system> <mount point> <type> <options> <dump> <pass>
UUID=c92d59c3-c9d0-4382-xxxx-x44e4e900d94 /home/1T ext4 defaults 0 1

```
