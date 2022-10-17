---
Title | cmake windows
-- | --
Created @ | `2022-01-02T08:40:46Z`
Last Modify @| `2022-10-17T09:13:46Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/244)

---
## Reference

- [BuildingWinDLL](https://gitlab.kitware.com/cmake/community/-/wikis/doc/tutorials/BuildingWinDLL)

## Brief


## Build dll


### Windows Tips


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

```
cmake -T "Intel C++ Compiler 2021" \
-D CMAKE_C_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
-D CMAKE_CXX_COMPILER="C:/Program Files (x86)/Intel/oneAPI/compiler/2021.2.0/windows/bin/icx.exe" \
..
```

- 使用 `CMAKE_GENERATOR_TOOLSET` 在 CMakeLists.txt 中定义 Solution toolset

```
set(CMAKE_GENERATOR_TOOLSET "Intel C++ Compiler 2022")
#set(CMAKE_GENERATOR_TOOLSET "Intel(R) oneAPI DPC++ Compiler 2022")
```

-  使用 `VS_PLATFORM_TOOLSET` 在 CMakeLists.txt 中定义 单个 Project toolset

```
set_target_properties(target PROPERTIES VS_PLATFORM_TOOLSET "Intel(R) oneAPI DPC++ Compiler 2022" )
```
> 添加在 target 后面


