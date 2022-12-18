---
Title | Linux Tools ls
-- | --
Created @ | `2019-07-25T06:28:25Z`
Last Modify @| `2022-12-18T06:06:34Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/109)

---
# Brief
- `ls` 列出文件夹下的内容

Target | Command | Comment
-- | -- | --
按时间排序 | `ls -tr` | -r 对目录反向排序<br>-t 以时间排序
查看详细时间戳 | ` ls -l --time-style=full `
按大小排序 | `ls -lrS` |  -S 以文件大小排序
统计文件夹文件数量 | `ls */* -d1|xargs -i sh -c 'echo {};ls {}|wc -l'`
列出子目录的完整路径 | `ls */* -d1`


# Issues

- home/user 目录下使用 `ls` 命令卡死无响应

```
sudo umount -f thinclient_drives
```
> `thinclient_drives` 是 `xrdp` 搭建产生的目录
