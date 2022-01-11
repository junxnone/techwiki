---
Title | DPCPP
-- | --
Create Date | `2021-10-28T08:00:47Z`
Update Date | `2022-01-11T01:54:03Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/193)

---
## Reference
- [DPC++ Spec](https://spec.oneapi.io/versions/latest/elements/dpcpp/source/index.html#)
- [oneAPI DPC++ Compiler documentation](https://intel.github.io/llvm-docs/GetStartedGuide.html)
- [Intel Data Parallel C++ (and SYCL 2020) Tutorial](https://github.com/jeffhammond/dpcpp-tutorial)
- [SYCL 1.2.1 spec](https://www.khronos.org/registry/SYCL/specs/sycl-1.2.1.pdf)
- [DPCPP API](https://intel.github.io/llvm-docs/doxygen/index.html) 
- [Intel llvm Implementaion](https://github.com/intel/llvm/tree/sycl/)
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
- [Level Zero](/Level_Zero)

## Arch


![image](https://user-images.githubusercontent.com/2216970/139390103-c0653884-e220-4509-a5da-acdc1514fdca.png)

### DPCPP Runtime

![image](https://user-images.githubusercontent.com/2216970/145666271-385828ff-8393-40e3-9605-03bbe52767a1.png)

![image](https://user-images.githubusercontent.com/2216970/145666277-1df7f586-32af-4152-8efa-83d0c293aebf.png)


### Compiler Pipeline

![image](https://user-images.githubusercontent.com/2216970/145666824-bba9f275-e0a0-4325-9056-569c0c966803.png)


## DPCPP VS OPENCL/CUDA/HIP

name | Description
-- | --
OPENCL/CUDA/HIP | - Low-level<br>- Separate source for device code<br>- Device code only
`DPC++(SYCL)`/OpenMP | - Higher-level<br>- Single source<br>- Host  and Device code
