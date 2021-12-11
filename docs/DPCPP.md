---
Title | DPCPP
-- | --
Create Date | `2021-10-28T08:00:47Z`
Update Date | `2021-12-11T06:02:07Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/193)

---
## Reference
- [DPC++ Spec](https://spec.oneapi.io/versions/latest/elements/dpcpp/source/index.html#)
- [oneAPI DPC++ Compiler documentation](https://intel.github.io/llvm-docs/GetStartedGuide.html)
- [Intel Data Parallel C++ (and SYCL 2020) Tutorial](https://github.com/jeffhammond/dpcpp-tutorial)
- [SYCL 1.2.1 spec](https://www.khronos.org/registry/SYCL/specs/sycl-1.2.1.pdf)
- [DPCPP API](https://intel.github.io/llvm-docs/doxygen/index.html)
- [Level Zero](https://dgpu-docs.intel.com/technologies/level-zero.html)
- [DPCPP Reference](https://oneapi-src.github.io/DPCPP_Reference/index.html)
- [training - intel](https://techdecoded.intel.io/quickhits/overview-of-oneapi-dpc-programming)

## Brief
- **DPC++** - `oneAPI Data Parallel C++` - Intel
- 数据并行编程/异构编程
- C++ 标准 > `C++17`
-  = `ISO C++` + `SYCL standard` + `extensions`
- 实现了 [SYCL](/SYCL) 接口
  - 使用 [OpenCL](/OpenCL) 后端加速 Intel CPU/iGPU/FPGAs
  - 使用 `CUDA+PTX` 后端加速 Nvidia GPUs


## Arch


![image](https://user-images.githubusercontent.com/2216970/139390103-c0653884-e220-4509-a5da-acdc1514fdca.png)

## DPCPP VS CUDA

name | Description
-- | --
CUDA | - Low-level<br>- Separate source for device code<br>- Device code only
`DPC++(SYCL)`/OpenMP | - Higher-level<br>- Single source<br>- Host  and Device code
