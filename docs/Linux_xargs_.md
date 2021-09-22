---
Title | Linux xargs 
-- | --
Create Date | `2021-09-22T06:41:38Z`
Update Date | `2021-09-22T06:41:38Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/110)

---
# Reference
- [每天学习一个命令：xargs ](https://einverne.github.io/post/2019/06/xargs)
- [xargs 说明](https://wangchujiang.com/linux-command/c/xargs.html)

# Brief

## Usecase

Usecase | cmd
-- | --
查找 `txt` 文件并打印 | `find . -name *.txt \| xargs cat `
查找 `mp4` 文件并 `copy` 到指定目录 | `find . -name *.mp4 \| xargs -i cp {} crop/`
执行多条命令 | `find . -name *.txt \| xargs -i  sh -c 'echo {}; cat {} \| grep xxx'`
默认替代符为 `{}`, 指定替代符 `%` | `find . -name *** \| xargs -I % sh -c 'echo %; cat % \| grep xxx'`
多个参数 | `echo "one" "two" "three" \| xargs -l sh -c 'echo $0, $1, $2' \| xargs`
从文件读取链接并下载 | `xargs -a links.txt -I {} wget {}`
并行执行 用于加速 | `printf %s\\n {0..99} \| xargs -n 1 -P 8  sh -c 'echo {}; sleep 2;'` <br> -n : 每次取几个参数<br> -P : 进程数

## Examples

-  **合并多行**

`f.txt`

```
a b c 
d e
f g h 
j i 
j k l
m n
```
```
$ cat f.txt |xargs -n 5
a b c d e
f g h j i
j k l m n
```


