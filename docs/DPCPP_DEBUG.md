---
Title | DPCPP DEBUG
-- | --
Create Date | `2022-01-18T03:26:23Z`
Update Date | `2022-01-21T07:22:11Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/250)

---
## Reference

- [Debug the Offload Process](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-programming-guide/top/software-development-process/debugging-the-dpc-and-openmp-offload-process/debug-the-offload-process.html)
- [OneAPI Debug Tools](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-programming-guide/top/software-development-process/debugging-the-dpc-and-openmp-offload-process/oneapi-debug-tools.html)


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

- 设置 打印 SYCL 跟踪 Log
```
set SYCL_PI_TRACE=1/2/-1
```
- 设置使用后端 OpenCL/Level_Zero
```
set SYCL_DEVICE_FILTER=opencl
set SYCL_DEVICE_FILTER=opencl:cpu
set SYCL_DEVICE_FILTER=opencl:gpu
set SYCL_DEVICE_FILTER=level_zero
set SYCL_DEVICE_FILTER=level_zero:gpu
```
- 设置显示 Level_Zero API Call
```
set ZE_DEBUG=1
```
