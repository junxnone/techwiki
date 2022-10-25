---
Title | DPCPP DEBUG
-- | --
Created @ | `2022-01-18T03:26:23Z`
Last Modify @| `2022-10-25T10:43:22Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/250)

---
## Reference

- [Debug the Offload Process](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-programming-guide/top/software-development-process/debugging-the-dpc-and-openmp-offload-process/debug-the-offload-process.html)
- [OneAPI Debug Tools](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-programming-guide/top/software-development-process/debugging-the-dpc-and-openmp-offload-process/oneapi-debug-tools.html)
- [Intercept Layer for OpenCL](https://github.com/intel/opencl-intercept-layer)
- [Level Zero Tracer](https://github.com/intel/pti-gpu/tree/master/tools/ze_tracer)

## Brief
- `sycl printf`
- Environment variables
- GDB
- Intercept Layer
- ze_tracer


## Use `printf` debug in DPCPP kernel

```
#ifdef __SYCL_DEVICE_ONLY__
#define CL_CONSTANT __attribute__((opencl_constant))
#else
#define CL_CONSTANT
#endif
#define PRINTF(format, ...) { \
            static const CL_CONSTANT char _format[] = format; \
            sycl::ext::oneapi::experimental::printf(_format, ## __VA_ARGS__); }
````

```
PRINTF("test PRINTF")
```

## Environment variables

- 设置 **SYCL_PI_TRACE** 打印 SYCL 跟踪 Log
```
set SYCL_PI_TRACE=1/2/-1
```
- 设置 **SYCL_DEVICE_FILTER** 使用后端 OpenCL/Level_Zero
```
set SYCL_DEVICE_FILTER=opencl
set SYCL_DEVICE_FILTER=opencl:cpu
set SYCL_DEVICE_FILTER=opencl:gpu
set SYCL_DEVICE_FILTER=level_zero
set SYCL_DEVICE_FILTER=level_zero:gpu
```
- 设置 **ZE_DEBUG** 显示 Level_Zero API Call
```
set ZE_DEBUG=1
```

## 使用 sycl-ls 查看设备
- sycl-ls/sycl-ls.exe 


```
$ sycl-ls
[opencl:acc:0] Intel(R) FPGA Emulation Platform for OpenCL(TM), Intel(R) FPGA Emulation Device 1.2 [2022.13.3.0.16_160000]
[opencl:cpu:1] Intel(R) OpenCL, Intel(R) Xeon(R) CPU E5-2678 v3 @ 2.50GHz 3.0 [2022.13.3.0.16_160000]
[host:host:0] SYCL host platform, SYCL host device 1.2 [1.2]
```
