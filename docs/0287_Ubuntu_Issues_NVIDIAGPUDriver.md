---
Title | Ubuntu Issues NVIDIAGPUDriver
-- | --
Created @ | `2022-05-24T02:51:47Z`
Last Modify @| `2022-12-22T08:13:18Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/287)

---

## Log

```
Failed to initialize NVML: Driver/library version mismatch
```

## Solution

- 1 查看哪些占用了 nvidia mod, kill 掉相关进程

```
sudo lsof -n -w /dev/nvidia*
```

- 2 卸载动态驱动 module

```
sudo rmmod nvidia
```
- 3 重新安装官网下载的驱动


