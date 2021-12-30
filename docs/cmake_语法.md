---
Title | cmake 语法
-- | --
Create Date | `2021-10-28T04:25:32Z`
Update Date | `2021-12-30T05:30:43Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/192)

---
## Reference

- [string](https://cmake.org/cmake/help/latest/command/string.html)
- [cmake 预定义变量](https://cmake.org/cmake/help/latest/manual/cmake-variables.7.html)
- [cmake 预定义语法/函数/宏](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html)

## Brief
- 变量
- string
- 条件控制
- 宏-函数
- 文件
- 项目
- 库
- 编译器
- **指令**大小写无关, **参数和变量**大小写相关

## 变量
- 自定义变量

WR | Examples
-- | --
写 | `SET(VAR "/opt/xxx")`
读 | `${VAR}`

- 系统环境变量

WR | Examples
-- | --
写 | `SET(ENV{VAR} "/opt/xxx")`
读 | `$ENV{VAR}`

- set()/unset()
- 预定义变量


常用预定义变量 | 描述
-- | --
`PROJECT_NAME` | 项目名称
`CMAKE_C_COMPILER` | C 编译器
`CMAKE_CXX_COMPILER` | C++ 编译器
`CMAKE_CXX_STANDARD` | C++ 标准
`CMAKE_INSTALL_PREFIX` | 安装位置
`CMAKE_MODULE_PATH` | 指定 CMake modules 查找路径 默认为空 (分号分隔的 list)
`WIN32` | **Windows**: `1` <br>**Linux**: False?None
`CMAKE_SYSTEM_NAME` | **Windows**: `Windows` <br>**Linux**: `Linux`



## string
- 查找/替换/正则匹配
- 拼接/大小写替换/sub-string/...
- 比较/Hash
- ... 详细见 [[cmake string](https://cmake.org/cmake/help/latest/command/string.html)]

### 常用 string 操作

Operations | Pattern | Description
-- | -- | --
FIND |  `string(FIND <string> <substring> <out-var> [...])`
REPLACE | `string(REPLACE <match-string> <replace-string> <out-var> <input>...)`
REGEX MATCH | `string(REGEX MATCH <match-regex> <out-var> <input>...)`
REGEX MATCHALL | `string(REGEX MATCHALL <match-regex> <out-var> <input>...)`
REGEX REPLACE | `string(REGEX REPLACE <match-regex> <replace-expr> <out-var> <input>...)`
TOLOWER | `string(TOLOWER <string> <out-var>)`
TOUPPER | `string(TOUPPER <string> <out-var>)`
LENGTH | `string(LENGTH <string> <out-var>)`
COMPARE | `string(COMPARE <op> <string1> <string2> <out-var>)`



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
`aux_source_directory(dir VAR)` | 添加目录`dir` 下的所有源码到变量 `VAR`
`add_definitions()`
`find_package()` | 
`set(VAR xxx)`<br>`set(VAR ${VAR} XXX)` | 设置变量值<br>追加值

### 源相关 & 依赖

Func | Description
-- | --
`INCLUDE_DIRECTORIES([AFTER\|BEFORE] [SYSTEM] dir1 [dir2 ...])` | 添加头文件
`ADD_SUBDIRECTORIES([source dir] [bin dir] [exclude_from_all])` | 添加子目录(CMakeLists.txt & src)
`find_library()` | 查找到指定的预编译库
`target_link_libraries()` | 设置需要链接的库


### 目标相关

Func | Description
-- | --
`project(demo)` | 设置项目名称
`add_executable(demo demo.cpp)` | 生成可执行文件
`add_library(common STATIC/SHARED  util.cpp)` | 生成静态库/动态库(默认是静态库)

