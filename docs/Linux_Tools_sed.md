---
Title | Linux Tools sed
-- | --
Create Date | `2021-09-19T10:11:29Z`
Update Date | `2021-09-19T10:11:29Z`
---
sed 是一种流编辑器，它是文本处理中非常中的工具，能够完美的配合正则表达式使用，功能不同凡响。处理时，把当前处理的行存储在临时缓冲区中，称为“模式空间”（pattern space），接着用sed命令处理缓冲区中的内容，处理完成后，把缓冲区的内容送往屏幕。接着处理下一行，这样不断重复，直到文件末尾。文件内容并没有 改变，除非你使用重定向存储输出。Sed主要用来自动编辑一个或多个文件；简化对文件的反复操作；编写转换程序等。


# Reference
- [ ] [sed](https://wangchujiang.com/linux-command/c/sed.html)
- [ ] [sed 删除文本中的内容](https://www.cnblogs.com/crazymagic/p/11147988.html)
# UseCase
## 插入
- 插入某行到指定行之前
```
sed  -i '3i\this is a insert line' test.txt
```
> 之后用 `sed -i '3a\xxxx' file`

- 在每行行首添加字符 `HEAD`
```
sed 's/^/HEAD&/g'  file
```
- 在每行行尾添加字符`TAIL`
```
sed 's/$/&TAIL/g'  file
```

## 删除

删除 | Commands
-- | --
删除字符 | `sed -i s#pattern##g filename`
删除包含 `xxx` 的行 | `sed -i '/xxx/d' filename`
删除以 `xxx` 开始的行 | `sed -i '/^xxx/d' filename`
删除第 `n` 行 | `sed -i 'nd' filename`
删除 `n ~ m` 行 | `sed -i 'n,md' filename`
删除最后一行 | `sed -i '$d' filename`
删除指定`变量`行号 | `sed -i "${var1},${var2}d" filename`
> 这里引号必须为双引号

## 替换
替换 | Commands
-- | --
替换 old 为 new | `sed -i s#old#new#g filename`
替换以 `1` 开头的字符串 为 `0`  | `sed -i 's/^1/0/g' filename`
替换特殊字符 使用 `\` 转义 | `sed -i #s/\“aab/bbc/g' filenam`
替换以`<path`开头，任意字符后跟着`\`的字符串为`path>` | `sed -i 's/\<path.*\\/path\>/g' *`
替换文件夹下的文件 | ``` sed -i s#old#new#g `grep -rl "old" .` ```
> 用于labelimg pascal voc 标记文件中 去掉 local path 
