---
Title | cmake
-- | --
Create Date | `2018-09-02T08:05:59Z`
Update Date | `2022-01-03T04:43:06Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/64)

---
## Reference
- [Mastering CMake](https://cmake.org/cmake/help/book/mastering-cmake/index.html)
- [2016-09-27-CMake-tutorial.pdf](https://github.com/junxnone/linuxwiki/files/7415584/2016-09-27-CMake-tutorial.pdf)
- [CMake Tutorial](https://cmake.org/cmake/help/latest/guide/tutorial/index.html) [[Tutorial Code](https://github.com/Kitware/CMake/tree/master/Help/guide/tutorial)]
- [Supported Compilers](https://cmake.org/cmake/help/git-master/manual/cmake-compile-features.7.html#supported-compilers)
- [An Introduction to Modern CMake](https://cliutils.gitlab.io/modern-cmake/)

## Brief
- **Build-System Generator** - 编译系统生成器(Not a Build-System)
- [Install](./cmake_install)
- [`CMakeLists.txt` 语法](./cmake_语法)
  - [cmake variables](/cmake_variables)
  - [cmake string]
  - [cmake condition]
  - [cmake debug](/cmake_debug)
  - [cmake platforms](/cmake_platforms)
  - [cmake target]
  - [cmake dependency]
  - [cmake interaction]
- [Usecase](./cmake_usecase)
  - [cmake windows](/cmake_windows)
- [ctest]
- [cpack](/cpack)
- [ccmake]
- [cmake-gui]
- [cmake Tutorial 分析](https://github.com/junxnone/CMake/issues/1)

## Supported

### Supported languages
- C/C++/CUDA/HIP/OBJC/OBJC++

![image](https://user-images.githubusercontent.com/2216970/138817820-b2abb50a-36c4-41ac-8d78-f7c0dcc40167.png)


### Supported Compilers

- AppleClang: Apple Clang for Xcode versions 4.4+.
- Clang: Clang compiler versions 2.9+.
- GNU: GNU compiler versions 4.4+.
- MSVC: Microsoft Visual Studio versions 2010+.
- SunPro: Oracle SolarisStudio versions 12.4+.
- Intel: Intel compiler versions 12.1+.

### Supported Project Tools

- Linux(`GNU make`/Ninja)
- Windows(`Visual Studio`/nmake)
- [Details](/cmake_generators)

## Cmake workflow

![image](https://user-images.githubusercontent.com/2216970/138798860-7ac0c8bb-116f-40d9-b6b3-78ed006e385c.png)

![image](https://user-images.githubusercontent.com/2216970/138817345-ab0f7e70-594c-4b37-b6b8-222384dea085.png)


