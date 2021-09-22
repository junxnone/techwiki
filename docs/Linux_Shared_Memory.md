---
Title | Linux Shared Memory
-- | --
Create Date | `2021-09-22T06:02:09Z`
Update Date | `2021-09-22T06:02:09Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/98)

---
# Reference
- [共享内存](https://cloud.tencent.com/developer/article/1536272)

# Brief
- 基于传统SYS V的共享内存
- 基于POSIX mmap文件映射实现共享内存
- 通过memfd_create()和fd跨进程共享实现共享内存
- 多媒体、图形领域广泛使用的基于dma-buf的共享内存
## POSIX API

API | Description
-- | --
shm_open() | 
mmap () 

## SYS V API
API | Description
-- | --
shm_open() | 
shmget() | 创建共享内存
shmat() |将共享内存段链接到进程地址空间
shmdt() |将共享内存脱离进程链接
shmctl() | 控制共享内存

## Shared memory 同步方式
- 信号量
- 互斥锁

# Tools

- ipcs 查看相关的 `shared  memory`
- 
