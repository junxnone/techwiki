---
Title | NUMA
-- | --
Create Date | `2021-11-19T15:23:28Z`
Update Date | `2021-11-19T15:23:28Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/224)

---
## Reference
- [NUMA架构的CPU](http://cenalulu.github.io/linux/numa/)
- [为什么 NUMA 会影响程序的延迟](https://draveness.me/whys-the-design-numa-performance/)
- [NUMA Support - MS](https://docs.microsoft.com/en-us/windows/win32/procthread/numa-support)
- [NUMA DEEP DIVE PART 4: LOCAL MEMORY OPTIMIZATION](https://frankdenneman.nl/2016/07/13/numa-deep-dive-4-local-memory-optimization/)

## Brief
- NUMA - `Non Uniform Memory Access/非统一内存访问`
  - SMP - `symmetric multiprocessor` - 对称处理器
- Node - [CPU, Memory]
- Optimization
  - 核绑定
    - Core 0 是系统调度核，避免绑定
  - 2 CPU/2 Instance
  - 线程数和物理核数一致

## UMA & NUMA

UMA | NUMA
-- | -- 
![image](https://user-images.githubusercontent.com/2216970/129500037-426a9e06-c2b4-4582-bd62-63291ec110f3.png) | ![image](https://user-images.githubusercontent.com/2216970/129500056-bff6bf41-27d7-44f7-a0e2-ff947108a4f5.png)


##  `Local Access` & `Remote Access`
- **Latency** -   `Local Access` < `Remote Access`

![image](https://user-images.githubusercontent.com/2216970/128668657-9ef9de73-c715-4472-be3c-6e85e64ea6ac.png) | ![image](https://user-images.githubusercontent.com/2216970/128667808-921a1c93-195f-48ef-b53e-7c528e402ddf.png)
-- | --

## 进程 & 内存 分配策略

- 进程
  - cpunodebind
  - phycpubind
- 内存
  - localalloc
  - preferred
  - membind
  - interleave

## UseCase
- Tools
  - numactl - Linux  
  - coreinfo.exe - Windows

----
- `numactl -H` 查看 `NUMA Node`
```
available: 2 nodes (0-1)
node 0 cpus: 0 2 4 6 8 10 12 14 16 18 20 22 24 26 28 30 32 34 36 38
node 0 size: 160990 MB
node 0 free: 38998 MB
node 1 cpus: 1 3 5 7 9 11 13 15 17 19 21 23 25 27 29 31 33 35 37 39
node 1 size: 112869 MB
node 1 free: 38065 MB
node distances:
node   0   1
  0:  10  21
  1:  21  10
```
> - node distances - 访问延迟 `Remote Access` 是 `Local Access` 的 2.1 倍

