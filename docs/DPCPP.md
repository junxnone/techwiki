---
Title | DPCPP
-- | --
Create Date | `2021-10-28T08:00:47Z`
Update Date | `2021-10-29T07:34:38Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/193)

---
# Reference
- [DPC++ Spec](https://spec.oneapi.io/versions/latest/elements/dpcpp/source/index.html#)
- [oneAPI DPC++ Compiler documentation](https://intel.github.io/llvm-docs/GetStartedGuide.html)
- [Intel Data Parallel C++ (and SYCL 2020) Tutorial](https://github.com/jeffhammond/dpcpp-tutorial)
- [SYCL 1.2.1 spec](https://www.khronos.org/registry/SYCL/specs/sycl-1.2.1.pdf)
- [DPCPP API](https://intel.github.io/llvm-docs/doxygen/index.html)
- [Level Zero](https://dgpu-docs.intel.com/technologies/level-zero.html)
- [DPCPP Reference](https://oneapi-src.github.io/DPCPP_Reference/index.html)


# Brief
- **DPC++** - `oneAPI Data Parallel C++` - Intel
-  = `ISO C++` + `SYCL standard` + `extensions`
- 数据并行编程/异构编程
- C++ 标准 > `C++17`
- [SYCL](/SYCL)

![image](https://user-images.githubusercontent.com/2216970/139390103-c0653884-e220-4509-a5da-acdc1514fdca.png)


name | Description
-- | --
CUDA | - Low-level<br>- Separate source for device code<br>- Device code only
`DPC++(SYCL)`/OpenMP | - Higher-level<br>- Single source<br>- Host  and Device code
