---
Title | Cache
-- | --
Create Date | `2022-04-25T03:29:21Z`
Update Date | `2022-04-25T03:55:43Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/273)

---
## Reference
- [计算机体系结构(Spring 2021)](http://staff.ustc.edu.cn/~xhzhou/CA-Spring2021/CA.html)  [[chapter04-01.pdf](https://github.com/junxnone/linuxwiki/files/8551388/chapter04-01.pdf)]
- [计算机体系结构-Cache高速缓存](https://zhuanlan.zhihu.com/p/482651908)

## Brief
- Cache - 高速缓冲存储器
  - 更快的读写数据
  - **时间局部性:** 一个数据如果当前被使用到，那么接下去一段时间它很可能被再次用到
  - **空间局部性:** 一个数据如果当前被使用到，那么接下去一段时间它周围的数据很可能也会被用到
- `L1 Cache`/`L2 Cache`/`L3 Cache`
- Data Block: 主存和Cache 会被分割成一定大小块, 相互映射读写
  - 直接映射/`Direct Mapped`
  - 组相联/`Set Associative`
  - 全相联/`Fully Associative`
- Cache Line: 主存中的 Data Block 映射到 Cache 中

## Cache Arch

![image](https://user-images.githubusercontent.com/2216970/165016896-a476cb9a-2cc7-4d4e-b1bc-289951c5e79f.png)

### 映射方式
- 直接映射/`Direct Mapped`:  每个主存 Block 只能映射到特定 `Cache Line`
- 组相联/`Set Associative`: Cache 分组 主存 Block 映射到组
- 全相联/`Fully Associative` : 可以放在任何位置

![image](https://user-images.githubusercontent.com/2216970/165017679-58109c88-1645-4171-9ca1-4e6fa9028f57.png)

映射方式 | Example
-- | --
全相联 | `Memory Block 12` 可以映射到 `Cache Block 0~7`
直接映射 |  `Memory Block 12` 可以映射到 `Cache Block 4` (12 MOD 8)
组相联 | `Memory Block 12` 可以映射到 `Set 0` (12 MOD 4)

> MOD - 取余


