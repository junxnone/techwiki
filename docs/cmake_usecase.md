---
Title | cmake usecase
-- | --
Create Date | `2021-07-15T06:05:14Z`
Update Date | `2021-10-26T01:54:25Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/65)

---
# Reference
- [wiki](https://gitlab.kitware.com/cmake/community/-/wikis/home)

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


