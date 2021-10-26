---
Title | cmake usecase
-- | --
Create Date | `2021-07-15T06:05:14Z`
Update Date | `2021-10-26T05:25:53Z`
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

## Variables
- VAR
- 引用变量: `${VAR}`
- set()
- 预定义变量

## BuildSystem

## Usecase

Description | args
-- | --
指定安装位置 | `-D CMAKE_INSTALL_PREFIX=/your/install/path`


## 常用语法

Func | Description
-- | --
`cmake_minimum_required(VERSION 3.4.1)` |  只当 cmake 最小版本
`project(demo)` | 设置项目名称
`add_executable(demo demo.cpp)` | 生成可执行文件
`add_library(common STATIC util.cpp)` | 生成静态库
`add_library(common SHARED util.cpp)` | 生成动态库/共享库
`aux_source_directory(dir VAR)` | 添加目录`dir` 下的所有源码到变量 `VAR`
`add_definitions()`
`add_subdirectory()`
`find_library()` | 查找到指定的预编译库
`find_package()` | 
`include_directories()` | 设置包含目录
`target_link_libraries()` | 设置需要链接的库
`set(VAR xxx)`<br>`set(VAR ${VAR} XXX)` | 设置变量值<br>追加值


## 条件控制
- `if..elseif..else...endif`
- `while...endwhile`
- `foreach..endforeach`
- `not`
- AND/OR/DEFINED - 变量
- EXISTS/IS_NEWER_THAN/IS_DIRECTORY - 文件
- LESS/GREATER/EQUAL - 数字比较
- STRLESS/STRGREATER/STREQUAL - 字母比较
- MATCHES - pattern regex


## log 打印信息
- `message`
