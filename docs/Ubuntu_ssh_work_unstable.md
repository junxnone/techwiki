---
Title | Ubuntu ssh work unstable
-- | --
Create Date | `2021-09-22T06:45:13Z`
Update Date | `2021-09-22T06:45:13Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/112)

---
# Issue Description

- ssh 不稳定，经常断开
- 有时候会连接不上
- mac地址 ： 88:88:88:88:87:88

## Root Cause
- 网卡 firmware 的mac 地址不对
- 网络中有mac 地址相同的device，被分配为同一IP

## Solution

`System Setting -> Network -> Options -> Ethernet -> Cloned MAC address`

> 此项更改为一个新的mac地址（和本地网络中device无重复）
> 重启。


