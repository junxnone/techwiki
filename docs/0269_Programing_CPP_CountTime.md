---
Title | Programing CPP CountTime
-- | --
Created @ | `2022-04-14T08:42:15Z`
Last Modify @| `2022-12-22T06:29:09Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/269)

---
## Reference
- [深入理解std::chrono的时钟Clock ](https://www.cnblogs.com/zhongpan/p/7490657.html)
- [`std::chrono::high_resolution_clock`简单测试](https://zhuanlan.zhihu.com/p/496261328)


## Brief
- `system_clock`
- `steady_clock`
- `high_resolution_clock`
- `std::chrono::clock`


## UseCase

UseCase | Code | Description
-- | -- | --
system_clock | `auto tp = std::chrono::system_clock::now();` | 系统时钟，可能被更改
steady_clock | `auto tp = std::chrono::steady_clock::now();` | 单调时钟，只会增长，用于计时
high_resolution_clock | `auto tp = std::chrono::high_resolution_clock::now();` | 高精度版本 `steady_clock`



### Example - steady_clock
```

#include <chrono>

#define TIMERSTART(tag)  auto tag##_start = std::chrono::steady_clock::now(),tag##_end = tag##_start
#define TIMEREND(tag)  tag##_end =  std::chrono::steady_clock::now()
#define DURATION_s(tag) printf("%s costs %d s\n",#tag,std::chrono::duration_cast<std::chrono::seconds>(tag##_end - tag##_start).count())
#define DURATION_ms(tag) printf("%s costs %d ms\n",#tag,std::chrono::duration_cast<std::chrono::milliseconds>(tag##_end - tag##_start).count());
#define DURATION_us(tag) printf("%s costs %d us\n",#tag,std::chrono::duration_cast<std::chrono::microseconds>(tag##_end - tag##_start).count());
#define DURATION_ns(tag) printf("%s costs %d ns\n",#tag,std::chrono::duration_cast<std::chrono::nanoseconds>(tag##_end - tag##_start).count());


// usage:
//   TIMERSTART(for_loop);
//   for (int i = 0; i < 100000; i++)
//   {
//       i*i;
//   }
//   TIMEREND(for_loop);
//   DURATION_ms(for_loop);
```
