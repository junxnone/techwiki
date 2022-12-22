---
Title | Build Cmake 语法
-- | --
Created @ | `2021-10-28T04:25:32Z`
Last Modify @| `2022-12-22T06:00:45Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/192)

---
## Reference

- [cmake 预定义变量](https://cmake.org/cmake/help/latest/manual/cmake-variables.7.html)
- [cmake 预定义语法/函数/宏](https://cmake.org/cmake/help/latest/manual/cmake-commands.7.html)
- [CMake链接外部库的几种方式](https://blog.csdn.net/liangshui999/article/details/106425753)



## Brief
- 变量
- 字符操作
- 文件操作
- 条件控制
- 宏-函数
- 项目
- 库
- 编译器
- **指令**大小写无关, **参数和变量**大小写相关


## 条件控制
- `if()/elseif()/else()/endif()`
- `while()/endwhile()`
- `foreach()/endforeach()`
  - `break()`
  - `continue()`
- `not`
- AND/OR/DEFINED - 变量
- EXISTS/IS_NEWER_THAN/IS_DIRECTORY - 文件
- LESS/GREATER/EQUAL - 数字比较
- STRLESS/STRGREATER/STREQUAL - 字母比较
- MATCHES - pattern regex


## 注释

- 单行注释

```
# comment line
```

- 多行注释

```
#[[ comment line 1
comment line 2
comment line 3
]]
```

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
`add_library(common STATIC/SHARED  util.cpp)` | 生成静态库/动态库(默认是静态库)<br> `BUILD_SHARED_LIBS` 变量可以设置 default 为 `SHARED`

