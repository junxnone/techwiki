---
Title | Tools 添加账户
-- | --
Created @ | `2019-02-19T10:38:10Z`
Last Modify @| `2022-12-21T10:24:22Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/130)

---
# 添加用户 adduser vs useradd

## Reference
- [linux用户管理（1）----创建用户（adduser和useradd）和删除用户（userdel）](https://blog.csdn.net/beitiandijun/article/details/41678251)

## adduser vs useradd
- adduser: 会自动为创建的用户指定主目录、系统shell版本，会在创建时输入用户密码。
- useradd: 需要使用参数选项指定上述基本设置，如果不使用任何参数，则创建的用户无密码、无主目录、没有指定shell版本。

