---
Title | cmake variables
-- | --
Created @ | `2021-12-30T06:57:59Z`
Last Modify @| `2022-10-20T13:06:58Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/240)

---
## Reference
- [cmake 预定义变量](https://cmake.org/cmake/help/latest/manual/cmake-variables.7.html)
- [Variables - CGold](https://cgold.readthedocs.io/en/latest/tutorials/variables.html)

## Brief
- 自定义变量
- 预定义变量
- 变量读写
- 常规变量 & 缓存变量
- 变量作用域
- List
- 系统环境变量

## 变量读写
- 写命令 set()/unset()
- 自定义变量
- 系统环境变量 例如 `ONEAPI_ROOT`

WR | 自定义变量读写 | 系统环境变量读写
-- | -- | --
写 | `SET(VAR "/opt/xxx")` | `SET(ENV{VAR} "/opt/xxx")`
读 | `${VAR}` | `$ENV{VAR}`


## 常用预定义变量

常用预定义变量 | 描述 | Values
-- | -- | --
`PROJECT_NAME` | 项目名称
`CMAKE_INSTALL_PREFIX` | 安装位置 | **Unix Defaults**: `/usr/local` <br>**Windows Defaults**: `c:/Program Files/${PROJECT_NAME}`
`CMAKE_MODULE_PATH` | 指定 CMake modules 查找路径 | 默认为空 (分号分隔的 list)


### 编译工具相关

常用预定义变量 | 描述 | Values
-- | -- | --
`CMAKE_C_COMPILER` | C 编译器
`CMAKE_CXX_COMPILER` | C++ 编译器
`CMAKE_CXX_STANDARD` | C++ 标准


### OS 相关

常用预定义变量 | 描述 | Values
-- | -- | --
`WIN32` | 是否是 Windows OS | **Windows**: `1` <br>**Linux**: `False?None`
`CMAKE_SYSTEM_NAME` | OS Name | **Windows**: `Windows` <br>**Linux**: `Linux`



### 目录相关

常用预定义变量 | 描述 | Values
-- | -- | --
`CMAKE_CURRENT_SOURCE_DIR` | 源码目录
`PROJECT_BINARY_DIR` | 编译目录



