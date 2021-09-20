---
Title | nmap
-- | --
Create Date | `2021-09-20T03:25:56Z`
Update Date | `2021-09-20T03:25:56Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/18)

---
# Reference

- [官网](https://nmap.org/)
- [Nmap详解](https://blog.csdn.net/qq_36119192/article/details/82079150)
- [docs - zh](https://nmap.org/man/zh/)

# Brief

Nmap是一款开源免费的网络发现（Network Discovery）和安全审计（Security Auditing）工具。

- 软件名字Nmap是Network Mapper的简称。
- Nmap最初是由Fyodor在1997年开始创建的。
- **功能**
  - 主机发现 (Host Discovery)
  - 端口扫描 (Port Scanning)
  - 版本侦测 (Version Detection)
  - 操作系统侦测 (Operating System Detection)


# UseCase

## 扫描端口

```
nmap -T4 -A -v  your_IP
```

- -T4 指定扫描过程使用的时序，总有6个级别（0-5），级别越高，扫描速度越快，但也容易被防火墙或IDS检测并屏蔽掉，在网络通讯状况较好的情况下推荐使用T4
- -A 选项用于使用进攻性方式扫描
- -v 表示显示冗余信息，在扫描过程中显示扫描的细节，从而让用户了解当前的扫描状态

```
nmap your_IP -p 20 -Pn
```

> -Pn : 不进行ping扫描

```
PORT   STATE    SERVICE
22/tcp filtered ssh

Nmap done: 1 IP address (1 host up) scanned in 2.09 seconds
```

**端口状态(PORT STATE)**

1. open：端口开放
2. closed：端口关闭
3. filtered：端口被防火墙IDS/IPS屏蔽，无法确定其状态
4. unfiltered：端口没有被屏蔽，但是否开放需要进一步确定
5. open|filtered：端口是开放或被屏蔽，Nmap不能识别
6. closed|filtered ：端口是关闭或被屏蔽，Nmap不能识别


## 版本侦测

```
nmap -sV your_IP
```
```
Host is up (0.00018s latency).
Not shown: 997 closed ports
PORT     STATE SERVICE       VERSION
22/tcp   open  ssh           OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
3389/tcp open  ms-wbt-server xrdp
5900/tcp open  vnc           VNC (protocol 3.7)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 6.41 seconds
```

## OS 侦测

```
nmap -O your_IP
```
```
Host is up (0.00038s latency).
Not shown: 997 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
3389/tcp open  ms-wbt-server
5900/tcp open  vnc
Device type: general purpose
Running: Linux 3.X|4.X
OS CPE: cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:4
OS details: Linux 3.2 - 4.8
Network Distance: 2 hops

OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 3.74 seconds
```

# 主机发现 (Host Discovery)

```
nmap -sP 192.168.1.0/24
```
