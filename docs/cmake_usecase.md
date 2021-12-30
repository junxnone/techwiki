---
Title | cmake usecase
-- | --
Create Date | `2021-07-15T06:05:14Z`
Update Date | `2021-12-30T05:28:43Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/65)

---
# Reference
- [wiki](https://gitlab.kitware.com/cmake/community/-/wikis/home)
- [Tutorial](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)


# Brief
- command-line mode
- Generate Makefiles
- Generate Visual Studio Solution

---
- Files 
  - CMakeLists.txt
  - `<script>.cmake`
  - `<module>.cmake`


## `CMakeLists.txt` UseCase

- 简单demo

```
cmake_minimum_required (VERSION 2.6)
project(demo)
add_executable(demo demo.cxx)
```

### 设置版本号

```
set(PROJECT_VERSION 1.0.1.1)
```
```
project(demo VERSION <major>[.<minor>[.<patch>[.<tweak>]]])
```

###  判断是否是 Windows 系统

```
if(WIN32)
  xxx
else()
  xxx
endif()
```
```
if(${CMAKE_SYSTEM_NAME} STREQUAL "Windows")
endif()
```


## CMDLine Usecase

Description | CMDLine args `cmake [xxx]`
-- | --
指定安装位置 | `-D CMAKE_INSTALL_PREFIX=/your/install/path`


