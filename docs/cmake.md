---
Title | cmake
-- | --
Create Date | `2018-09-02T08:05:59Z`
Update Date | `2021-10-26T02:24:42Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/64)

---
# Reference
- [CMake常用命令](https://www.jianshu.com/p/8909efe13308)
- [Downloads](https://cmake.org/files/)
- [Ubuntu16.04下安装Cmake-3.8.2](https://blog.csdn.net/l1216766050/article/details/77513045)

# Brief
- [Install](./cmake_install)
- [Usecase](./cmake_usecase)




# Issues
- **cmake generate `VS2019` Solution with `Intel Compiler` solution**

```
cmake -T "Intel C++ Compiler 2021" \
-D CMAKE_C_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
-D CMAKE_CXX_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
..
```

