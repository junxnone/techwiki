---
Title | Linux IPC Semaphore
-- | --
Created @ | `2021-01-19T03:09:42Z`
Last Modify @| `2022-12-22T07:40:12Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/99)

---
# Reference
- [Linux基础（四）——信号量与PV操作](https://blog.csdn.net/lixiangsheng2012/article/details/83421359)

# Brief
- 进程互斥
- 进程同步

## PV 操作 
- 来源于 `荷兰语` - 通过(passeren)/释放(vrijgeven)
- PV 操作 不可中断
- P 操作
  - `S=S-1`
  - `S >= 0` 则继续执行, 否则阻塞等待，进入等待队列
- V 操作
  - `S=S+1`
  - `S >0`   则继续执行，否则释放等待队列中的第一个进程

## 用于互斥
- S 初始为 1
- 进程 1 进行 P 操作 S = 0, 继续执行
- 进程 2 进行 P 操作 S = -1，进入等待队列
- 进行1 执行完临界区，进行 V 操作 S = 0, 释放等待队列中的进程 2
- 进程 2 执行 临界区，执行完后进行 V 操作 S =1

> 进程 1 & 2 不能同时进入临界区，当有一个先进入后，另一个只能等待资源释放

## 用于同步
 
```
//Write
while(TRUE){
     P(empty);
     write_data();
     V(full);
}

//Read
while(True){
   P(full);
   read_data();
   V(empty);
}
```
- empty_S = 1/ full_S = 0
- Write 进程 
  - P 操作  empty_S - 1 = 0,  写数据
  - V 操作 full_S + 1 = 1
  - 第二次 P 操作 empty_S - 1 = -1, 阻塞等待
- Read 进程 
  - P 操作 full_S - 1 = -1, 阻塞等待
  - 当 full_S = 0 时，释放 Read 进程，读取数据
  - V 操作 empty_S + 1 = 0, 释放 Write 进程
