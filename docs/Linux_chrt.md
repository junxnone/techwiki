---
Title | Linux chrt
-- | --
Create Date | `2021-10-09T03:36:01Z`
Update Date | `2021-10-09T03:38:31Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/167)

---
# Brief
- 管理进程实时属性


# UseCase

UseCase | Cmd
-- | --
查看进程的优先级和调度策略 | `chrt -p [pid]`
查看进程的所有线程的优先级和调度策略  |`chrt -a -p [pid]`
查看每种调度策略对应的优先级范围 | `chrt -m`
设置进程的调度策略 | `chrt -f -p [prio] [pid]`<br>`chrt -r -p [prio] [pid]`
把进程的所有线程都变成实时调度 | `chrt -r -p -a [prio] [pid]`
指定优先级和调度策略来启动一个进程 | `chrt -f <priority between 1-99> <command>`

