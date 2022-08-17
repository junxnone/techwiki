---
Title | Increase Swap
-- | --
Created @ | `2022-08-17T08:56:29Z`
Last Modify @| `2022-08-17T08:56:29Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/291)

---
## Reference
- [Ubuntu 20.04增加SWAP分区](https://blog.csdn.net/weixin_37532614/article/details/119239715)


## Steps

Steps & Description | Command
-- | --
查看 swap | `free -h`
关闭 swap | `sudo swapoff`
删除旧 swap | `sudo rm /swapfile`
查看硬盘空间，决定合适的 swap 大小 | `df -h`
创建分区 | `sudo fallocate -l 8G /swapfile`
查看创建的分区 | `ls-lh /swapfile`
更改权限 | `sudo chmod 600 /swapfile`
创建 swap 分区 | `sudo mkswap /swapfile`
打开 swap 功能 | `sudo swapon /swapfile`
查看 swap 状态 | `sudo swapon --show`

