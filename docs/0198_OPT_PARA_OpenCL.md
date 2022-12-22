---
Title | OPT PARA OpenCL
-- | --
Created @ | `2021-01-25T07:01:15Z`
Last Modify @| `2022-12-22T05:42:49Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/198)

---
# Reference
- [OpenCL - wikipedia](https://en.wikipedia.org/wiki/OpenCL)
- [OpenCL简介](https://blog.csdn.net/XianBT/article/details/18914273)
- [组织官网](http://www.khronos.org/)
- [OpenCL 官网](https://www.khronos.org/opencl/)
- [OpenCL Guide](https://github.com/KhronosGroup/OpenCL-Guide)
- [OpenCL Resource](https://www.khronos.org/opencl/resources)
- [OpenCL 2.0 异构计算 [第三版] （Heterogeneous Computing with OpenCL 2.0）](https://www.bookstack.cn/books/Heterogeneous-Computing-with-OpenCL-2.0)

# Brief
- OpenCL - Open Computing Language - 开放计算机语言
- 一个用于异构(CPU/GPU/DSP) 编程的框架/规范
- 定义了API，硬件底层实现由各公司实现 (Intel/NVIDIA/AMD)
- `OpenCL ICD` - `Installable Client Driver Loader` 加载 `Vendor ICDs`
- [OpenCL Install](/OpenCL_Install)
- **一些实现**
  - [Intel(R) Graphics Compute Runtime for OpenCL](https://github.com/intel/compute-runtime)
  - [AMD ROCm](https://rocmdocs.amd.com/en/latest/)
  - [TI OpenCL-DSP](https://downloads.ti.com/mctools/esd/docs/opencl/index.html)
  - [POCL -  Portable Computing Language](http://portablecl.org/)
  - [NVIDIA OpenCL SDK](https://developer.nvidia.com/opencl) - 非开源
- 使用 OpenCL 作为后端的 语言/库
  - Caffe
  - SYCL
  - OpenCV
  - OpenACC
  - Tensorflow
  - Halide
  - C++ AMP
  - ...


## Low level Parallel Programing

![image](https://user-images.githubusercontent.com/2216970/127420583-54ee5a20-aba8-494c-b673-b9b607fbdbc8.png)

## Higher & Lower Level Languages

![image](https://user-images.githubusercontent.com/2216970/127420728-9ddc8970-7c55-4b52-935f-06756bb046c7.png)


# History

