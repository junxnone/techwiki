---
Title | CPP 计时
-- | --
Create Date | `2022-04-14T08:42:15Z`
Update Date | `2022-04-18T07:50:19Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/269)

---
## Reference
- [深入理解std::chrono的时钟Clock ](https://www.cnblogs.com/zhongpan/p/7490657.html)
- [std\:\:chrono\:\:high_resolution_clock简单测试](https://zhuanlan.zhihu.com/p/496261328)


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
