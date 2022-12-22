---
Title | Programing Python time
-- | --
Created @ | `2018-09-03T23:32:30Z`
Last Modify @| `2022-12-22T06:39:04Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/266)

---
## Reference
- [time — Time access and conversions](https://docs.python.org/3/library/time.html)

## Brief
- 自带 时间处理 模块

## UseCase

Use Case | Function
-- | -- 
时间戳 | time.time()
当前时间格式化字符串 | time.strftime("%Y_%m_%d_%H_%M_%S")
延时 | time.sleep(n)


## Examples

- **time.sleep()**
> Python time sleep() 函数推迟调用线程的运行，可通过参数secs指秒数，表示进程挂起的时间。
挂起程序以避免占用cpu.

```
import time 
print("Start:" + time.ctime())
time.sleep( 5 )
print("End :" + time.ctime())
```
```
Start:Tue Sep  4 07:43:05 2018
End :Tue Sep  4 07:43:10 2018
```

