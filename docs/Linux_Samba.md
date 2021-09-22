---
Title | Linux Samba
-- | --
Create Date | `2021-09-22T06:49:12Z`
Update Date | `2021-09-22T06:49:12Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/113)

---
# Reference
- [win10访问不了samba共享文件夹解决方法](https://jingyan.baidu.com/article/7c6fb428d62a6e80642c90cc.html) 
- [Ubuntu下samba配置和使用](https://jingyan.baidu.com/article/3a2f7c2ed314ef26afd611a1.html)
- [Samba服务安装配置](https://www.cnblogs.com/erick2/p/5877521.html)
- [Samba+Windows: Allow multiple connections by different users?](https://superuser.com/questions/95872/sambawindows-allow-multiple-connections-by-different-users)
- [ubuntu samba服务器多用户配置](https://www.cnblogs.com/sky-heaven/p/5181234.html)

# Brief

## Install & Setup
- **Install samba**
```
sudo apt install -y samba smbclient
```
- **Setup - add share folder**
```
sudo vi /etc/samba/smb.conf
```

```
[share]
   comment = share folder
   browseable = yes
   writable = yes
   path = /home/xxx/share
   create mask = 0777
   directory mask = 0777
   valid users = xxx
   force user = nobody
   force group = nogroup
   public = yes
   available = yes
```
> 不使用密码 `guest ok = yes`

- set user samba password
```
sudo smbpasswd -a xxx
```
- restart samba service
```
sudo systemctl restart smbd.service
```

## Login
## Windows 带有域名
- 如果我们在带有域名的前提下输入用户名，是无法通过验证的，所以我们需要在用户名前加一个`\`符号 - `\user_1`

### Windows 多用户登录同一server
- windows 不允许 多用户名密码 同时登录同一server
- 重新登录前需要 cmd -> `net use * /del /y`
- 或者 需要两个用户同时使用的目录使用 `valid users = user_1 user_2`

## Ubuntu

**安装cifs支持**

```
sudo apt-get install cifs-utils
```
```
sudo mount -t cifs //xxxx.xxx.xxx.xxx/share /your/path/ -o username=xxx,password=xxx
```


