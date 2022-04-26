---
Title | Performance Optimization
-- | --
Create Date | `2022-04-25T02:05:42Z`
Update Date | `2022-04-26T02:25:29Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/272)

---
## Reference
- [Optimize - Intel® oneAPI Programming Guide](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-programming-guide/top/software-development-process/performance-tuning-cycle/optimize.html)
- [Software optimization resources](https://www.agner.org/optimize/)
- [TMA_自顶向下的CPU架构性能瓶颈分析方法](https://zhuanlan.zhihu.com/p/60569271)
- [《A Top-Down Method for Performance Analysis and Counters Architecture》阅读笔记](https://andrewei1316.github.io/2020/12/20/top-down-performance-analysis/)
- [自顶向下的微架构分析方法 - Intel](https://www.intel.com/content/www/us/en/develop/documentation/vtune-cookbook-zh-cn/top/methodologies/top-down-microarchitecture-analysis-method.html)
2014 **TMA** [A Top-Down method for performance analysis and counters architecture.pdf](https://github.com/junxnone/linuxwiki/files/8559242/A.Top-Down.method.for.performance.analysis.and.counters.architecture.pdf)


## Brief
- 性能优化
- 时间复杂度
- 空间复杂度
- 并行化
  - [[SIMD]]
  - [[OpenMP]]
  - [[SYCL]]
  - [[DPCPP]
  - [[OpenCL]]
- [内存优化/Memory Optimizations](/Memory_Optimizations)
- [Loop Optimizations](/Loop_Optimizations)
- 加速库
  - [IPP - Intel](/IPP_Intel)
  - [MKL - Intel](/MKL_Intel)
- Tools
  - [[Vtune]]
  - [pmu tools](https://github.com/andikleen/pmu-tools)
- **PMUs**: CPU 内核中的专用逻辑块，用于记录计算系统上发生的特定硬件事件(缓存遗漏/分支错误预测), 这些事件组合起来创建有用的高级指标，如 CPI 。



## TMA
- TMA - `Top-Down Microarchitecture Analysis`

