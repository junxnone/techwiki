---
Title | Ubuntu watch
-- | --
Created @ | `2019-03-05T05:16:10Z`
Last Modify @| `2022-12-22T07:50:58Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/54)

---
## Brief
- 监测一个命令的运行结果

## UseCasse

Usecase | cmd
-- | --
监控 GPU | `watch -n 1 nvidia-smi`
监控log文件变化 | `watch -d  ' ls -l \| grep log '`
查看网络连接 | `watch -n 1 -d netstat  -ant`
