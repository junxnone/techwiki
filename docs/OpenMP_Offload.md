---
Title | OpenMP Offload
-- | --
Create Date | `2021-11-03T05:56:24Z`
Update Date | `2021-11-03T08:17:08Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/204)

---
# Reference

- [Get Started with OpenMP* Offload to GPU for the Intel® oneAPI DPC++/C++ Compiler and Intel® Fortran Compiler](https://www.intel.com/content/www/us/en/develop/documentation/get-started-with-cpp-fortran-compiler-openmp/top.html)
- [OpenMP offload compilers](https://github.com/ye-luo/openmp-target/wiki/OpenMP-offload-compilers)
- [Introduction to oneAPI and OpenMP* Offload with C/C++](https://github.com/oneapi-src/oneAPI-samples/blob/master/DirectProgramming/C%2B%2B/Jupyter/OpenMP-offload-training/intro/intro.ipynb)


# Brief
- OpenMP 支持 Device Code 在 Intel/AMD/NVIDIA GPU 上运行
- OpenMP 4.0+ 开始支持


```
...// Sequential Host Code

#pragma omp target     //Target Region Executed on the Device
{
    for (...) {
        ...;
    }
}
...// More Sequential Host Code
```

```
export OMP_TARGET_OFFLOAD={"MANDATORY" | "DISABLED" | "DEFAULT" }
- MANDATORY:  run on GPU
- DISABLED: run on CPU
- DEFAULT GPU --> Fall back to CPU
```

### API

API | Description
-- | --
`omp_get_default_device()` | 返回默认的 `Target Device`
`omp_set_default_device()` | 设置默认的 `Target Device`
`omp_get_num_devices()` | 返回 `Target Device` 的数量
`omp_get_device_num()` | 返回当前 `thread` 执行的 `Device Number`
`omp_is_initial_device()` | 返回当前 `thread` 是否执行在 `Host Device`
`omp_get_initial_device()` | 返回 `Host Device` 的 `Device Number`


###  Compiler Option

Compiler Option | Description
-- | --
`-fopenmp-targets=spir64` | [Intel Compiler](/Intel_Compiler) 选项使编译器产生 `x86 + SPIR64` 用于 iGPU
`-fopenmp-targets=amdgcn-amd-amdhsa` | AMD AOMP
`-mp=gpu -gpu=cc70` | NVIDIA HPC

### VS DPCPP(SYCL)
- OpenMP 适合迁移 `C/Fortran` 应用
- DPCPP(SYCL) 适合迁移 CUDA/OpenCL 应用
