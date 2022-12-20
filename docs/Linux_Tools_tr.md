---
Title | Linux Tools tr
-- | --
Created @ | `2019-08-22T09:40:46Z`
Last Modify @| `2022-12-20T08:48:22Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/107)

---
# Reference
- [Linux tr命令](https://www.runoob.com/linux/linux-comm-tr.html)

# Brief
- Linux tr 命令用于转换或删除文件中的字符。

tr 指令从标准输入设备读取数据，经过字符串转译后，将结果输出到标准输出设备。

## UseCase

Usecase | cmd
-- | --
替换大小写 | `cat testfile \| tr a-z A-Z`
替换空格为逗号 | `cat log.txt \| tr ' ' ','`


