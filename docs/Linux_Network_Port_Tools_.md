---
Title | Linux Network Port Tools 
-- | --
Create Date | `2021-09-20T03:29:34Z`
Update Date | `2021-09-20T03:29:34Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/19)

---
# Reference
- [Linux 查看端口占用情况](https://www.runoob.com/w3cnote/linux-check-port-usage.html)

# Tools
- lsof
- netstat
- [nmap](./nmap)

## lsof

UseCase | Command
-- | --
查看指定端口  | lsof -i:1200
查看使用的端口 | lsof -i

##  netstat

UseCase | Command
-- | --
查看指定端口  | `sudo netstat -anp\|grep 6015`



