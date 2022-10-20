---
Title | cmake windows
-- | --
Created @ | `2022-01-02T08:40:46Z`
Last Modify @| `2022-10-20T12:57:52Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/244)

---
## Reference

- [BuildingWinDLL](https://gitlab.kitware.com/cmake/community/-/wikis/doc/tutorials/BuildingWinDLL)
- [cmkae - import library](https://cmake.org/cmake/help/latest/manual/cmake-buildsystem.7.html#archive-output-artifacts)

## Brief


## Build dll
- shared library - `add_library(target_name SHARED C_CPP_FILES)`

### import library

- windows 创建动态库 时会自动创建 import lib, 但是前提是必须存在符号导出

> This file is only guaranteed to exist if the library exports at least one unmanaged symbol.


### Windows Tips


###  判断是否是 Windows 系统
- 三个变量
  - **WIN32=1** : `定义 project(project_name)` 之前就会被定义
  - **CMAKE_SYSTEM_NAME=Windows**: `定义 project(project_name)` 之后才会被定义
  - **MSVC=1**: `定义 project(project_name)` 之后才会被定义


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
### Windows 替换路径 `\` 为 `/`

```
string(REPLACE "\\" "/" NEW_PATH $ENV{OS_PATH})
```

### 添加源文件
- 添加 math 子目录
```
add_subdirectory(xxx)
```
- 

###  Generate `VS2019` Solution with `Intel Compiler`

#### 设置整个 Solution 编译工具

- 使用 `CMAKE_GENERATOR_TOOLSET` 在 CMakeLists.txt 中定义 Solution toolset
  - 需要在 `project(project_name)` 之前设置, 否则不生效

```
set(CMAKE_GENERATOR_TOOLSET "Intel C++ Compiler 2022")
#set(CMAKE_GENERATOR_TOOLSET "Intel(R) oneAPI DPC++ Compiler 2022")
```

#### 设置单个 Project 的编译工具

-  使用 `VS_PLATFORM_TOOLSET` 在 CMakeLists.txt 中定义 单个 Project toolset

```
set_target_properties(target PROPERTIES VS_PLATFORM_TOOLSET "Intel(R) oneAPI DPC++ Compiler 2022" )
```
> 添加在 target 后面

#### 使用命令行模式在生成 Solution 时设置


```
cmake -T "Intel C++ Compiler 2021" \
-D CMAKE_C_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
-D CMAKE_CXX_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
..
```
