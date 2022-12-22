---
Title | Programing Python Decorator
-- | --
Created @ | `2021-04-08T08:24:42Z`
Last Modify @| `2022-12-22T06:32:05Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/253)

---
## Reference
- [python装饰器(Decorator)-从基本原理到实践操作](https://blog.csdn.net/weixin_45690272/article/details/103206614)
- [python decorator心得体会](https://blog.csdn.net/lpstudy/article/details/43637717)
- [Python 装饰器执行顺序迷思](https://segmentfault.com/a/1190000007837364)


## Brief
-  - Decorator - 装饰器
- **用途**
  - 测试函数执行时间
  - 添加log/记录log
  - 查询 cache
  - 扩展已有函数(单参数--> list)


## Examples
### 计算函数执行时间

```
def timeit(method):
    def timed(*args, **kw):
        ts = time.time()
        result = method(*args, **kw)
        te = time.time()
        if 'log_time' in kw:
            name = kw.get('log_name', method.__name__.upper())
            kw['log_time'][name] = int((te - ts) * 1000)
        else:
            print '%r  %2.2f ms' % \
                  (method.__name__, (te - ts) * 1000)
        return result
    return timed

@timeit
def get_all_employee_details(**kwargs):
    print 'employee details'
```

- 打印函数名，并添加参数
```
from functools import wraps

time_cnt = 0
time_mean = 0
time_sum = 0
def get_time(mean_cnt):
    def mid(func):
        @wraps(func)
        def inner(*arg,**kwargs):
            global time_cnt, time_mean, time_sum, MEAN_CNT
            time_cnt += 1
            s_time = time.time()
            res = func(*arg,**kwargs)
            run_time = time.time() - s_time

            time_mean += run_time
            time_sum += run_time
            if time_cnt%mean_cnt == 0:
                print('{} mean({})：{:.6f} sec |  mean({})：{:.6f} sec'.format(func.__name__, mean_cnt, time_mean/mean_cnt, time_cnt, time_sum/time_cnt))
                time_mean = 0
            return res
        return inner
    return mid


@get_time(100)
def exec_func():
   xxxx
   ....
   

```
