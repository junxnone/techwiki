---
Title | OpenMP Offload
-- | --
Create Date | `2021-11-03T05:56:24Z`
Update Date | `2021-11-03T06:09:42Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/204)

---
# Reference

- [Get Started with OpenMP* Offload to GPU for the Intel® oneAPI DPC++/C++ Compiler and Intel® Fortran Compiler](https://www.intel.com/content/www/us/en/develop/documentation/get-started-with-cpp-fortran-compiler-openmp/top.html)
- [OpenMP offload compilers]()


# Brief
- OpenMP 支持 Device Code 在 Intel/AMD/NVIDIA GPU 上运行

###  Compiler Option

Compiler Option | Description
-- | --
`-fopenmp-targets=spir64` | [Intel Compiler](/Intel_Compiler) 选项使编译器产生 `x86 + SPIR64` 用于 iGPU
`-fopenmp-targets=amdgcn-amd-amdhsa` | AMD AOMP
`-mp=gpu -gpu=cc70` | NVIDIA HPC



