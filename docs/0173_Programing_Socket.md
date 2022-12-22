---
Title | Programing Socket
-- | --
Created @ | `2021-01-12T02:13:41Z`
Last Modify @| `2022-12-22T06:45:40Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/173)

---
## Reference
- [socket 简介](http://c.biancheng.net/view/2123.html)
- [socket samples](https://github.com/shineyr/Socket)

## Brief
- Socket - 套接字
- Server - Client
- TCP/IP/UDP 传输层 之上
- UNIX 
  - `Open-Read-Write-Close` - `Connect-Recv-Send-Disconnect`

----
![image](https://user-images.githubusercontent.com/2216970/104260621-d476b180-54be-11eb-9de3-798e07b584a3.png) | ![image](https://user-images.githubusercontent.com/2216970/104263724-1d316900-54c5-11eb-9137-3ff99a2303b8.png)
-- | --


## C API

API | Description | Server | Client
-- | -- | -- | --
socket() |  创建 socket |  ✅ | ✅
bind() | 绑定地址端口 | ✅ | ❌ 
listen() | 监听 | ✅| ❌
accept() | 接受连接 | ✅| ❌
connect() | 尝试连接| ❌ | ✅
send() <br> write() <br>writev() <br>sendmsg()<br> sendto() | 发送数据| ✅ | ✅
recv() <br> read() <br> writev() <br> recvmsg() <br> recvfrom()| 接收数据| ✅ | ✅
close()<br> shutdown() | 关闭连接
setsockopt()<br>getsockopt() | 设置/获取 socket 选项


### 创建 socket
`int socket(int domain, int type, int protocol)`

- domain

Parameters | Description
-- | -- 
AF_INET | IPv4 地址
AF_INET6 | IPv6 地址
AF_LOCAL/AF_UNIX | 绝对路径名
AF_ROUTE | 

- type

Parameters | Description
-- | -- 
SOCK_STREAM | 数据流
SOCK_DGRAM | 数据报
SOCK_RAW
SOCK_PACKET | 
SOCK_SEQPACKET | 有序分组

- protocol

Parameters | Description
-- | -- 
IPPROTO_TCP | TCP传输协议 `Transmission Control Protocl`
IPPTOTO_UDP | UDP传输协议 `Unix Datagram Protocol`
IPPROTO_SCTP | STCP传输协议
IPPROTO_TIPC | TIPC传输协议

> SOCK_STREAM不可以跟IPPROTO_UDP组合


### Bind
`int bind(int sockfd, const struct sockaddr *addr, socklen_t addrlen)`


