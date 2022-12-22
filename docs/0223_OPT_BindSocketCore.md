---
Title | OPT BindSocketCore
-- | --
Created @ | `2021-08-12T05:42:22Z`
Last Modify @| `2022-12-22T03:55:28Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/223)

---
## Reference
- [CPU Affinity Mask Calculator](https://bitsum.com/tools/cpu-affinity-calculator/)
- [NUMA node](https://support.microsoft.com/en-us/topic/you-cannot-specify-a-numa-node-when-you-create-a-process-by-using-the-start-command-in-windows-server-2008-r2-or-in-windows-7-59fc2cb8-ab6b-0a74-dc18-49139176c31b)


## Brief
- 绑定程序运行主线程的 创建 (0/1 socket  or Core)

## Windows
- none NUMA
```
C:\Windows\System32\cmd.exe /C start  /affinity 0x0000008000000000 your_app.exe
```

- ### NUMA Arch
```
C:\Windows\System32\cmd.exe /C start /node 0 /affinity 0x0000008000000000 your_app.exe
```
```
C:\Windows\System32\cmd.exe /C start /node 0  your_app.exe
```

## Linux

```
numactl
```


