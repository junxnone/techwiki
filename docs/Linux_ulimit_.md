---
Title | Linux ulimit 
-- | --
Create Date | `2021-09-22T07:29:32Z`
Update Date | `2021-09-22T07:29:32Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/126)

---


# Reference
- [ulimit: open files: cannot modify limit: Operation not permitted](https://blog.csdn.net/leshami/article/details/8749773)
- [ulimit 命令详解](https://www.cnblogs.com/zengkefu/p/5649407.html)


# Brief
- 多用户系统，限制用户使用资源

> 显示（或设置）用户可以使用的资源的限制（limit），这限制分为软限制（当前限制）和硬限制（上限），其中硬限制是软限制的上限值，应用程序在运行过程中使用的系统资源不超过相应的软限制，任何的超越都导致进程的终止。

- 配置文件：/etc/security/limits.conf
- --soft即是软限制，hard是硬限制。用户可以超过soft设置的值，但一定不能超过hard 的值。
