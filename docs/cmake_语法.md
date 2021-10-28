---
Title | cmake 语法
-- | --
Create Date | `2021-10-28T04:25:32Z`
Update Date | `2021-10-28T05:57:09Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/192)

---
# Reference

- [string](https://cmake.org/cmake/help/latest/command/string.html)
- [cmake 预定义变量](https://cmake.org/cmake/help/latest/manual/cmake-variables.7.html)
- [cmake 预定义语法/函数/宏](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html)


## Variables
- VAR
- 引用变量: `${VAR}`
- set()/unset()
- 预定义变量


常用预定义变量 | 描述
-- | --
PROJECT_NAME | 项目名称
CMAKE_INSTALL_PREFIX | 安装位置



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


