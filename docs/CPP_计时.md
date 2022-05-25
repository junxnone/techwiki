---
Title | CPP 计时
-- | --
Created @ | `2022-04-14T08:42:15Z`
Last Modify @| `2022-05-25T02:52:13Z`
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

UseCase | Code
-- | --
system_clock | `auto tp = std::chrono::system_clock::now();`
steady_clock | `auto tp = std::chrono::steady_clock::now();`
high_resolution_clock | `auto tp = std::chrono::high_resolution_clock::now();`
