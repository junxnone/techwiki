---
Title | cmake
-- | --
Create Date | `2018-09-02T08:05:59Z`
Update Date | `2021-10-28T07:33:31Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/64)

---
# Reference
- [CMake常用命令](https://www.jianshu.com/p/8909efe13308)
- [Downloads](https://cmake.org/files/)
- [Ubuntu16.04下安装Cmake-3.8.2](https://blog.csdn.net/l1216766050/article/details/77513045)
- [Mastering CMake](https://cmake.org/cmake/help/book/mastering-cmake/index.html)
- [2016-09-27-CMake-tutorial.pdf](https://github.com/junxnone/linuxwiki/files/7415584/2016-09-27-CMake-tutorial.pdf)

# Brief
- [Install](./cmake_install)
- [语法](./cmake_语法)
- [Usecase](./cmake_usecase)
- [ctest]
- [cpack](/cpack)
- [ccmake]
- [cmake-gui]

## Supported languages
- C/C++/CUDA/HIP/OBJC/OBJC++

![image](https://user-images.githubusercontent.com/2216970/138817820-b2abb50a-36c4-41ac-8d78-f7c0dcc40167.png)


## [Supported Compilers](https://cmake.org/cmake/help/git-master/manual/cmake-compile-features.7.html#supported-compilers)

- AppleClang: Apple Clang for Xcode versions 4.4+.
- Clang: Clang compiler versions 2.9+.
- GNU: GNU compiler versions 4.4+.
- MSVC: Microsoft Visual Studio versions 2010+.
- SunPro: Oracle SolarisStudio versions 12.4+.
- Intel: Intel compiler versions 12.1+.


## Cmake workflow

![image](https://user-images.githubusercontent.com/2216970/138798860-7ac0c8bb-116f-40d9-b6b3-78ed006e385c.png)

![image](https://user-images.githubusercontent.com/2216970/138817345-ab0f7e70-594c-4b37-b6b8-222384dea085.png)

# Issues
- **cmake generate `VS2019` Solution with `Intel Compiler` solution**

```
cmake -T "Intel C++ Compiler 2021" \
-D CMAKE_C_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
-D CMAKE_CXX_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
..
```

