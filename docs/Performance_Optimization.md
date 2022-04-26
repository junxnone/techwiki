---
Title | Performance Optimization
-- | --
Create Date | `2022-04-25T02:05:42Z`
Update Date | `2022-04-26T06:21:27Z`
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
- 性能优化 - 优化程序运行时间/内存占用/计算资源利用率
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
- Prefetch
- 加速库
  - [IPP - Intel](/IPP_Intel)
  - [MKL - Intel](/MKL_Intel)
- Tools
  - [[Vtune]]
  - [pmu tools](https://github.com/andikleen/pmu-tools)
- **PMUs**: CPU 内核中的专用逻辑块，用于记录计算系统上发生的特定硬件事件(缓存遗漏/分支错误预测), 这些事件组合起来创建有用的高级指标，如 CPI 。



## TMA
- TMA - `Top-Down Microarchitecture Analysis`
- **Front End**: 从内存中拉取指令并将指令翻译为微操作（micro-operations, μops），这些 μops 会被传递给后端部分，但通常这些 μops 会暂存在 ready-μops-queue 中。
- **Back End**: 以原始程序中的顺序调度（schedule）、执行（execute）和提交（commit, retire）这些 μops

![image](https://user-images.githubusercontent.com/2216970/165234008-d2226b5f-9fee-4eb7-8b2a-2fa14a24ddc4.png)

