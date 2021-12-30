---
Title | cmake variables
-- | --
Create Date | `2021-12-30T06:57:59Z`
Update Date | `2021-12-30T06:57:59Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/240)

---
## Reference
- [cmake 预定义变量](https://cmake.org/cmake/help/latest/manual/cmake-variables.7.html)

## Brief
- 自定义变量
- 预定义变量
- 变量读写

## 变量读写
- 写命令 set()/unset()

WR | 自定义变量读写 | 系统环境变量读写
-- | -- | --
写 | `SET(VAR "/opt/xxx")` | `SET(ENV{VAR} "/opt/xxx")`
读 | `${VAR}` | `$ENV{VAR}`


## 常用预定义变量

常用预定义变量 | 描述 | Values
-- | -- | --
`PROJECT_NAME` | 项目名称
`CMAKE_C_COMPILER` | C 编译器
`CMAKE_CXX_COMPILER` | C++ 编译器
`CMAKE_CXX_STANDARD` | C++ 标准
`CMAKE_INSTALL_PREFIX` | 安装位置
`CMAKE_MODULE_PATH` | 指定 CMake modules 查找路径 默认为空 (分号分隔的 list)
`WIN32` | 是否是 Windows OS | **Windows**: `1` <br>**Linux**: `False?None`
`CMAKE_SYSTEM_NAME` | OS Name | **Windows**: `Windows` <br>**Linux**: `Linux`


