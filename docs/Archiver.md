---
Title | Archiver
-- | --
Create Date | `2021-09-20T03:38:55Z`
Update Date | `2021-09-20T03:38:55Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/22)

---
# Tools

- tar
- zip/unzip
- 7z
- rar/unrar

# tar - `tar.gz` - `tar.bz2`

用法 | command
-- | --
压缩 `tar.gz` | `tar zvcf data.tar.gz data/`
解压 `tar.gz` | `tar zvxf data.tar.gz`
查看 `tar.gz` | `tar tvf data.trar.gz`
压缩 `tar.bz2` | `tar jvcf data.tar.bz2 data/`
解压 `tar.bz2` | `tar jvxf data.tar.bz2`
查看 `tar.bz2` | `tar jtvf data.trar.bz2`


# zip/unzip

用法 | command
-- | --
压缩 | `zip -q -r data.zip data/
解压  | `unzip data.zip`<br>`unzip data.zip -d tmp`

- zip

```
-a 将文件转成ASCII模式
-F 尝试修复损坏的压缩文件
-h 显示帮助界面
-m 将文件压缩之后，删除源文件
-n 特定字符串 不压缩具有特定字尾字符串的文件
-o 将压缩文件内的所有文件的最新变动时间设为压缩时候的时间
-q 安静模式，在压缩的时候不显示指令的执行过程
-r 将指定的目录下的所有子目录以及文件一起处理
-S 包含系统文件和隐含文件（S是大写）
```

- unzip

```
-n 解压缩时不要覆盖原有的文件；
-o 不必先询问用户，unzip执行后覆盖原有的文件；
-P [密码] 使用zip的密码选项；
-q 执行时不显示任何信息；
-d [目录] 指定文件解压缩后所要存储的目录；
```

# 7z

用法 | command
-- | --
压缩 | `7z a data.7z  data/`
解压 | `7z x data.7z`

# rar/unrar

用法 | command
-- | --
压缩 | `rar a data.rar data/`
解压 | `unrar x test.rar /path/to/extract`

