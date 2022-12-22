---
Title | OPT Tools Vtune
-- | --
Created @ | `2018-09-28T05:35:41Z`
Last Modify @| `2022-12-22T03:43:11Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/227)

---
## Reference
- [VTune](https://software.intel.com/en-us/vtune)
- [Parallel Matrix Multiplication - Code Samples of Intel(R) VTune(TM) Profiler](https://github.com/oneapi-src/oneAPI-samples/tree/master/Tools/VTuneProfiler)
- [性能测试工具VTune的功能和用法介绍](https://blog.csdn.net/WY_stutdy/article/details/79106501)
- [VTune工具的安装与基本使用](https://zzqcn.github.io/perf/intel_vtune/intro.html)

## Brief
- 分析性能
- **Support Devices** - CPU/GPU/FPGA
- **What**
  - Launch Application
  - Profile System
- **How**  
  - Hotspots
  - Microarchitecture
- [Vtune Command Line](/Vtune_Command_Line)


VTune可视化性能分析器（Intel VTune Performance Analyzer）是一个用于分析和优化程序性能的工具，作为Intel为开发者提供的专门针对寻找软硬件性能瓶颈的一款分析工具，它能确定程序的热点（hotspot），找到导致性能不理想的原因，从而让开发者据此对程序进行优化。

VTune性能分析器能通过以下的手段发现和定位程序中的性能问题：
 
- 从当前系统中收集性能数据；
- 从系统到源代码不同的层次上，以不同的互动形式来组织和展示数据；
- 发现潜在的性能问题，并提出改进措施。



## UseCase

- [Cache line 问题](https://zzqcn.github.io/perf/cpu_cache.html)
- [onapi devcloud](https://jupyter.oneapi.devcloud.intel.com/)/oneAPI_Essentials/06_Intel_VTune_Profiler

![image](https://user-images.githubusercontent.com/2216970/115494180-b2e44d80-a297-11eb-9a11-c17217227f38.png)

