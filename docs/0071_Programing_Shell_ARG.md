---
Title | Programing Shell ARG
-- | --
Created @ | `2020-06-18T07:00:43Z`
Last Modify @| `2022-12-22T06:44:03Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/71)

---
## 添加 help

```
if [ "$1" == "-h" ]; then
  echo "Usage:
  echo "    `basename $0`   [somestuff]"
  exit 0 
fi
```

> `$0` 为当前脚本名字, 只在使用如下方式执行时有效: `./script.sh`  & `sh script.sh`,  使用 source 时无效: `source script.sh`
> 使用 source 时可以使用  `${BASH_SOURCE}` 代替 `$0`


**for source script.sh**
- `exit 0` => `return`
- `basename $0` => `your script name`

## arguments

- 判断参数个数不对(`此处为3`), 显示帮助信息

```
if [ $# -ne 3 ];then
  echo "Usage:"
  echo "     your_script.sh [arg 1] [arg 2] ... [arg n]"
  return
fi
```

## 设置默认参数

- 若未设置参数 `$1` `$2` ，则使用后面的 default_model
- 若设置参数 `$1` `$2`, 则使用 `$1` `$2`

```
#!/bin/bash
default_model=yourmodel
model=${1:-$default_model}

default_testset=your_testset
testset=${2:-$default_testset}
```
