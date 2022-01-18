---
Title | DPCPP DEBUG
-- | --
Create Date | `2022-01-18T03:26:23Z`
Update Date | `2022-01-18T03:26:23Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/250)

---
## Reference

- [Debug the Offload Process](https://www.intel.com/content/www/us/en/develop/documentation/oneapi-programming-guide/top/software-development-process/debugging-the-dpc-and-openmp-offload-process/debug-the-offload-process.html)

## Use `print` debug in DPCPP kernel

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
