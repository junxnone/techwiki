---
Title | Ubuntu watch
-- | --
Create Date | `2021-09-20T13:21:47Z`
Update Date | `2021-09-20T13:21:47Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/54)

---
# Brief
- 监测一个命令的运行结果

# UseCasse

Usecase | cmd
-- | --
监控 GPU | `watch -n 1 nvidia-smi`
监控log文件变化 | `watch -d  ' ls -l \| grep log '`
查看网络连接 | `watch -n 1 -d netstat  -ant`
