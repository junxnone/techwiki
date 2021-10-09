---
Title | Linux chrt
-- | --
Create Date | `2021-10-09T03:36:01Z`
Update Date | `2021-10-09T03:36:27Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/167)

---
# Brief
- 管理进程实时属性


# UseCase

UseCase | Cmd
-- | --
查看进程的优先级和调度策略 | 
查看进程的所有线程的优先级和调度策略  |
查看每种调度策略对应的优先级范围 |
设置进程的调度策略 |
把进程的所有线程都变成实时调度 |
指定优先级和调度策略来启动一个进程 | `chrt -f <priority between 1-99> <command>`

