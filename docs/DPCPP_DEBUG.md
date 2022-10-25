---
Title | DPCPP DEBUG
-- | --
Created @ | `2022-01-18T03:26:23Z`
Last Modify @| `2022-10-25T10:45:06Z`
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


- Linux

```
$ sycl-ls
[opencl:acc:0] Intel(R) FPGA Emulation Platform for OpenCL(TM), Intel(R) FPGA Emulation Device 1.2 [2022.13.3.0.16_160000]
[opencl:cpu:1] Intel(R) OpenCL, Intel(R) Xeon(R) CPU E5-2678 v3 @ 2.50GHz 3.0 [2022.13.3.0.16_160000]
[host:host:0] SYCL host platform, SYCL host device 1.2 [1.2]
```

- Windows

```
C:\Program Files (x86)\Intel\oneAPI>sycl-ls 
[opencl:acc:0] Intel(R) FPGA Emulation Platform for OpenCL(TM), Intel(R) FPGA Emulation Device 1.2 [2022.14.7.0.30_160000]                                                                                                                      
[opencl:cpu:1] Intel(R) OpenCL, Intel(R) Core(TM) i5-8350U CPU @ 1.70GHz 3.0 [2022.14.7.0.30_160000]                    
[opencl:gpu:2] Intel(R) OpenCL HD Graphics, Intel(R) UHD Graphics 620 3.0 [31.0.101.2114]                               
[ext_oneapi_level_zero:gpu:0] Intel(R) Level-Zero, Intel(R) UHD Graphics 620 1.3 [1.3.0]                                
[host:host:0] SYCL host platform, SYCL host device 1.2 [1.2]                                                                                                                                 
```
