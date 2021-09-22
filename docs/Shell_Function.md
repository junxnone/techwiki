---
Title | Shell Function
-- | --
Create Date | `2021-09-22T02:00:13Z`
Update Date | `2021-09-22T02:00:13Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/75)

---
# Reference
- [linux shell function - runnoob](https://www.runoob.com/linux/linux-shell-func.html)

# Basic

```
function parse_somethine(){
   # do something
   return int;
}
parse_somethine $1 $2
```

# 默认参数

默认参数 | 说明
-- | --
$# | 传递到脚本的参数个数
$* | 以一个单字符串显示所有向脚本传递的参数
$$ | 脚本运行的当前进程ID号
$! | 后台运行的最后一个进程的ID号
$@ | 与$*相同，但是使用时加引号，并在引号中返回每个参数。
$- | 显示Shell使用的当前选项，与set命令功能相同。
$? | 显示最后命令的退出状态。0表示没有错误，其他任何值表明有错误。

# Examples

## copy 某处文件到指定处并以路径重命名文件

```
#!/bin/bash

function parse_dir(){
    ls $1 > tmpf.txt
    while read line
    do
        nname=`echo $line|awk '{ gsub(/\//,"_");print $0 }'`
        echo $nname
        cp "$line" "$2/$nname"
    done < tmpf.txt
}
parse_dir '20190805/defect1/*' dataset/defect1/
```

