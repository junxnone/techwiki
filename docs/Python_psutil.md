---
Title | Python psutil
-- | --
Create Date | `2021-03-10T05:45:34Z`
Update Date | `2022-03-29T09:19:05Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/263)

---
## Reference
- [Docs](https://psutil.readthedocs.io/en/latest/)

## Brief
-  获取系统信息


## UseCase

UC | Func
-- | --
获取 CPU 数量(逻辑核/超线程) | `psutil.cpu_count()`
物理核数量 | `psutil.cpu_count(logical=False)`
CPU time | `psutil.cpu_times()`
统计 CPU 使用率| `psutil.cpu_percent(interval=1, percpu=True)`
内存信息 | `psutil.virtual_memory()`
硬盘信息 |`psutil.disk_partitions()`
磁盘使用情况 | `psutil.disk_usage('/')`
磁盘IO | `psutil.disk_io_counters()`
获取网络读写字节／包的个数 | `psutil.net_io_counters()`
获取网络接口信息 | `psutil.net_if_addrs()`
获取网络接口状态 | `psutil.net_if_stats()`
网络连接信息 | `psutil.net_connections()`
进程信息 | `psutil.pids()`

