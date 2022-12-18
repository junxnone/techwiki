---
Title | Linux Tools rsync
-- | --
Created @ | `2019-07-11T09:46:59Z`
Last Modify @| `2022-12-18T06:04:57Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/32)

---
## Reference
- [rsync命令比对文件及增量同步](https://www.cnblogs.com/keithtt/p/7293733.html)
- [rsync man](https://www.cnblogs.com/f-ck-need-u/p/7221713.html) 
- [rsync(一)：基本命令和用法](https://www.cnblogs.com/f-ck-need-u/p/7220009.html)
- [服务器间同步inotify+rsync+supervisor](https://blog.csdn.net/liy819/article/details/52125769)
- [rsync+sersync单向文件实时同步配置详解](http://www.madown.com/2017/05/10/47/)
- [每天学习一个命令：使用 rsync 增量同步备份文件 ](https://einverne.github.io/post/2017/07/rsync-introduction.html)
 
## Brief
- rsync基于ssh协议实现的同步工具
- **三种常用同步方式**
  - 本地文件同步
  - 远程本地同步 - 使用 shell
  - 远程本地同步 - 使用 daemon
- **常用模式：** `rsync -avz --progress  src user@host:~/tgt/`

**常用参数**
```
-a --archive  ：归档模式，表示递归传输并保持文件属性。等同于 -rtopgDl
-t --times：保持 mtime 属性。强烈建议任何时候都加上 -t，否则目标文件 mtime 会设置为系统时间，导致下次更新检查出 mtime 不同从而导致增量传输无效。
-z：传输时进行压缩提高效率。
-r --recursive：递归到目录中去。
--password-file：daemon模式时的密码文件，可以从中读取密码实现非交互式。注意，这不是远程shell认证的密码，而是rsync模块认证的密码。
```

- **源路径如果是一个目录，带斜线和不带斜线是不一样的**
  - 不带斜线表示整个目录包括目录本身
  - 带斜线表示目录中的文件，不包括目录本身


## 1 本地文件同步
- 同步 `src` 到 `tgt`

```
rsync -av src tgt
```

- **显示进度** `--progress`

```
rsync -av --progress src tgt
```

## 2 远程本地同步 - 使用 shell
- **同步 `user@host:~/src` 到本地 `tgt`**

```
rsync -r --progress user@host:~/src/ tgt
```

- **同步本地 `src` 到远程 `user@host:~/tgt`**

```
rsync -r --progress  src user@host:~/tgt/
```
> 需要输入密码

## 3 远程本地同步 - 使用 daemon

```
rsync --daemon
```

- **rsyncd.conf**

```
[ftp1]
        path = /home/ftp
        comment = ftp export area
```

## 经常需要备份的文件

- 数据
- 软件配置文件
  - samba 配置文件
  - rsync 配置文件
  - tmux 配置文件
  - cron
  - supervisord

