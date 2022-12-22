---
Title | Performance Optimization
-- | --
Created @ | `2022-04-25T02:05:42Z`
Last Modify @| `2022-12-22T03:38:29Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/272)

---
# 性能优化

## Reference
- [Optimize - Intel® oneAPI Programming Guide](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-programming-guide/top/software-development-process/performance-tuning-cycle/optimize.html)
- [Software optimization resources](https://www.agner.org/optimize/)


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
- [TMA - Top-Down Microarchitecture Analysis](/Performance_Optimization_TMA)

## 相关名词
- **Front End**: 从内存中拉取指令并将指令翻译为微操作（micro-operations, μops），这些 μops 会被传递给后端部分，但通常这些 μops 会暂存在 ready-μops-queue 中。
- **Back End**: 以原始程序中的顺序调度（schedule）、执行（execute）和提交（commit, retire）这些 μops
- **Stall**:  阻塞, CPU 等待数据, 未工作(资源竞争/数据读写)
- **IPC**: `Instructions per cycle` 每时钟周期运行的指令数
- **CPI**: `Cycles per Instruction` 每条指令的平均时钟周期数
- **主频**: CPU 运行频率
- **时钟周期**: 时钟频率倒数
- **机器周期** - CPU 周期: 基本操作/元操作 周期(从内存里面读取一条指令的最短时间)
- **指令周期**: 取出一条指令并执行这条指令的时间
- **MIPS** - `Million Instructions Per Second` : 每秒执行百万条指令数
- **MFLOPS**- `Million Floating-point Operations per Second`: 每秒百万浮点数运算
- **PMUs**: CPU 内核中的专用逻辑块，用于记录计算系统上发生的特定硬件事件(缓存遗漏/分支错误预测), 这些事件组合起来创建有用的高级指标，如 CPI 。

