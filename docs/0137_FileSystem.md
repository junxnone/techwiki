---
Title | FileSystem
-- | --
Created @ | `2019-10-14T03:19:49Z`
Last Modify @| `2022-12-21T08:44:44Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/137)

---
# Linux File System

## proc

- 文件
```
- /proc/loadavg      前三列分别保存最近1分钟，5分钟，及15分钟的平均负载。
- /proc/meminfo    当前内存使用信息
- /proc/diskstats    磁盘I/O统计信息列表
- /proc/net/dev      网络流入流出统计信息
- /proc/filesystems  支持的文件系统
- /proc/cpuinfo        CPU的详细信息
- /proc/cmdline      启动时传递至内核的启动参数，通常由grub进行传递
- /proc/mounts     系统当前挂在的文件系统
- /proc/uptime    系统运行时间
- /poc/version     当前运行的内核版本号等信息
```
- 进程文件夹
```
- /proc/xxx/cmdline: 保存了当前进程的启动命令
- /proc/xxx/cwd: 一个符号链接，执行进程的运行目录
- /proc/xxx/exe: exe是一个软链接，指向进程的可执行文件，通过它可以启动当前进程的一个拷贝
- /proc/xxx/environ: 当前进程关联的环境变量。
- /proc/xxx/fd: 进程打开的每一个文件的文件描述符，指向实际文件的符号链接。可以通过它恢复删除的文件

```
