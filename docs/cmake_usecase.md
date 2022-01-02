---
Title | cmake usecase
-- | --
Create Date | `2021-07-15T06:05:14Z`
Update Date | `2022-01-02T04:02:53Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/65)

---
## Reference
- [wiki](https://gitlab.kitware.com/cmake/community/-/wikis/home)
- [Tutorial](https://cmake.org/cmake/help/latest/guide/tutorial/index.html)


## Brief
- command-line mode
- Generate Makefiles
- Generate Visual Studio Solution

---
- Files 
  - CMakeLists.txt
  - `<script>.cmake`
  - `<module>.cmake`


## UseCase

### 简单demo

```
cmake_minimum_required (VERSION 2.6) # 兼容的 cmake  最小版本
project(demo)  # 项目名称
add_executable(demo demo.cxx) # 使用 demo.cxx 生成可执行文件 demo
```

### 设置版本号

```
set(PROJECT_VERSION 1.0.1.1) # 单独设置版本号
```
```
project(Tutorial VERSION 1.0) # 设置项目名称时设置版本号
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

## CMDLine Usecase

Description | CMDLine args `cmake [xxx]`
-- | --
指定安装位置 | `-D CMAKE_INSTALL_PREFIX=/your/install/path`


