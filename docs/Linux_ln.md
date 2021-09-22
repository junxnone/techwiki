---
Title | Linux ln
-- | --
Create Date | `2021-09-22T06:16:16Z`
Update Date | `2021-09-22T06:16:16Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/103)

---
# Reference
- [Linux中软连接和硬连接的区别](https://www.cnblogs.com/loliconinvincible/p/12442230.html)

# Brief
- 软链接 - `symbolic link`
- 硬链接 - `hard link`

## 软链接 - 符号链接 - symbolic link

- 创建快捷方式
  - 源目录删除，软链接失效
  - 可以创建目录的软链接
  - 可以跨文件系统

```
ln -s src_dir your_dir
```
```
$ ln -s test test_1
$ ln -s test test_2
$ ll
-rw-r--r--  1 xxx xx 29 Mar  8 15:33 test
lrwxrwxrwx  1 xxx xx  4 Mar  8 15:34 test_1 -> test
lrwxrwxrwx  1 xxx xx  4 Mar  8 15:34 test_2 -> test
```

## 硬链接 - hard link

- 不创建文件副本，为指向文件索引(只有索引为1时删除才会删除数据)
- 不可以跨文件系统(例如两个硬盘)
- 不能创建目录的硬链接

```
$ ln  test test_3
$ ln  test test_4
$ ll
-rw-r--r--  3 xxx xx  29 Mar  8 15:33 test
lrwxrwxrwx  1 xxx xx  4 Mar  8 15:34 test_1 -> test
lrwxrwxrwx  1 xxx xx  4 Mar  8 15:34 test_2 -> test
-rw-r--r--  3 xxx xx  29 Mar  8 15:33 test_3
-rw-r--r--  3 xxx xx  29 Mar  8 15:33 test_4
```
> `test3` `test4` 为硬链接, 所以引用数变为 `3`

---
- 删除原文件 `test` 后
  - 软链接 `test_1` `test2` 不可用
  - 硬链接 `test_3` `test4` 可用, 引用数变为 `2`
  - 硬链接 `test_3` `test4` 可以访问内容
  - 更改 硬链接 `test_3` 的内容, `test4` 也会改变

```
$ rm test
$ ll
lrwxrwxrwx  1 xxx xx      4 Mar  8 15:34 test_1 -> test
lrwxrwxrwx  1 xxx xx      4 Mar  8 15:34 test_2 -> test
-rw-r--r--  2 xxx xx     29 Mar  8 15:33 test_3
-rw-r--r--  2 xxx xx     29 Mar  8 15:33 test_4
```

