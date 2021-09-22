---
Title | Shell arguments
-- | --
Create Date | `2021-09-22T01:51:58Z`
Update Date | `2021-09-22T01:51:58Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/71)

---

# help

```
if [ "$1" == "-h" ]; then
  echo "Usage:
  echo "    `basename $0`   [somestuff]"
  exit 0 
fi
```

> `basename` only works with `./script.sh` , not `source script.sh`
**for source script.sh**
- `exit 0` => `return`
- `basename $0` => `your script name`

# arguments

- 判断参数个数不对(`此处为3`), 显示帮助信息

```
if [ $# -ne 3 ];then
  echo "Usage:"
  echo "     your_script.sh [arg 1] [arg 2] ... [arg n]"
  return
fi
```

