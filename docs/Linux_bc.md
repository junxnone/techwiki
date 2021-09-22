---
Title | Linux bc
-- | --
Create Date | `2021-09-22T06:28:53Z`
Update Date | `2021-09-22T06:28:53Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/106)

---
# Brief
-  shell 中用于浮点计算

## UseCase

- **1 直接使用**

```
$ bc
bc 1.07.1
Copyright 1991-1994, 1997, 1998, 2000, 2004, 2006, 2008, 2012-2017 
Free Software Foundation, Inc.
This is free software with ABSOLUTELY NO WARRANTY.
For details type `warranty'.
3.5*10
35.0
```

- **2 使用 echo & | 管道**

```
$ echo "3.5*10"|bc
35.0
```

- **3 使用scale 保留小数位数**
```
$ echo "scale=2;1/3"|bc
.33
```
**当结果只有小数时，不显示整数怎么办？**
```
$ echo "scale=2;1/3"|bc|awk '{printf "%.2f", $0}'
0.33
```
**或者**
```
$ printf "%.2f\n" `echo "scale=2;1/3" | bc`
0.33
```
