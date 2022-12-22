---
Title | Build Cmake Platforms
-- | --
Created @ | `2022-01-02T06:35:43Z`
Last Modify @| `2022-12-22T06:03:04Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/243)

---
## Reference

- [Platform Checking](https://gitlab.kitware.com/cmake/community/-/wikis/doc/tutorials/How-To-Write-Platform-Checks#platform-checking)

## Brief
- Platform Variables
- CMake System Variables
  - `CMAKE_SYSTEM`
  - `CMAKE_SYSTEM_NAME`
  - `CMAKE_SYSTEM_VERSION`
  - `CMAKE_SYSTEM_PROCESSOR`
  - `CMAKE_HOST_SYSTEM_NAME`
- Compiler Checking
  - `CMAKE_<LANG>_COMPILER_ID`
  - `CMAKE_<LANG>_COMPILER_VERSION`
  - `CMAKE_<LANG>_COMPILER`
  - `CMAKE_<LANG>_COMPILER_LOADED`

Platform Variables | Description
-- | --
`UNIX` |  is TRUE on all UNIX-like OS's, including Apple OS X and *CygWin*
`WIN32` | is TRUE on Windows. Prior to 2.8.4 this included *CygWin*
`APPLE` | is TRUE on Apple systems. Note this does *not* imply the system is Mac OS X, only that **APPLE** is #defined in C/C++ header files.
`MINGW` | is TRUE when using the MinGW compiler in Windows
`MSYS` | is TRUE when using the MSYS developer environment in Windows
`CYGWIN` | is TRUE on Windows when using the *CygWin* version of cmake


CMAKE_SYSTEM_NAME | Environments Where Seen
-------|-------------------------
`Windows` | Windows (Visual Studio, MinGW GCC) 
`Darwin` | macOS/OS X (Clang, GCC) 
`Linux` | Linux (GCC, Intel, PGI) 
`Android` | Android NDK (GCC, Clang) 
`FreeBSD` | FreeBSD 
`CrayLinuxEnvironment` | Cray supercomputers (Cray compiler) 
`MSYS` | Windows (MSYS2 shell native GCC) 


## Examples

```
message(STATUS "CMAKE_SYSTEM IS ${CMAKE_SYSTEM}")
message(STATUS "CMAKE_SYSTEM_NAME IS ${CMAKE_SYSTEM_NAME}")
message(STATUS "CMAKE_SYSTEM_VERSION IS ${CMAKE_SYSTEM_VERSION}")
message(STATUS "CMAKE_SYSTEM_PROCESSOR IS ${CMAKE_SYSTEM_PROCESSOR}")
message(STATUS "CMAKE_HOST_SYSTEM_NAME IS ${CMAKE_HOST_SYSTEM_NAME}")
message(STATUS "UNIX IS  ${UNIX}")
message(STATUS "CMAKE_C_COMPILER_ID IS  ${CMAKE_C_COMPILER_ID}")
message(STATUS "CMAKE_CXX_COMPILER_ID IS  ${CMAKE_CXX_COMPILER_ID}")
message(STATUS "CMAKE_C_COMPILER_VERSION IS  ${CMAKE_C_COMPILER_VERSION}")
message(STATUS "CMAKE_CXX_COMPILER_VERSION IS  ${CMAKE_CXX_COMPILER_VERSION}")
message(STATUS "CMAKE_C_COMPILER IS  ${CMAKE_C_COMPILER}")
message(STATUS "CMAKE_CXX_COMPILER IS  ${CMAKE_CXX_COMPILER}")
message(STATUS "CMAKE_C_COMPILER_LOADED IS  ${CMAKE_C_COMPILER_LOADED}")
message(STATUS "CMAKE_CXX_COMPILER_LOADED IS  ${CMAKE_CXX_COMPILER_LOADED}")
```
- **Linux**
```
-- CMAKE_SYSTEM IS Linux-5.11.0-40-generic
-- CMAKE_SYSTEM_NAME IS Linux
-- CMAKE_SYSTEM_VERSION IS 5.11.0-40-generic
-- CMAKE_SYSTEM_PROCESSOR IS x86_64
-- CMAKE_HOST_SYSTEM_NAME IS Linux
-- UNIX IS  1
-- CMAKE_C_COMPILER_ID IS  GNU
-- CMAKE_CXX_COMPILER_ID IS  GNU
-- CMAKE_C_COMPILER_VERSION IS  9.3.0
-- CMAKE_CXX_COMPILER_VERSION IS  9.3.0
-- CMAKE_C_COMPILER IS  /usr/bin/cc
-- CMAKE_CXX_COMPILER IS  /usr/bin/c++
-- CMAKE_C_COMPILER_LOADED IS  1
-- CMAKE_CXX_COMPILER_LOADED IS  1
```
- **Windows**
```
-- CMAKE_SYSTEM IS Windows-10.0.19042
-- CMAKE_SYSTEM_NAME IS Windows
-- CMAKE_SYSTEM_VERSION IS 10.0.19042
-- CMAKE_SYSTEM_PROCESSOR IS AMD64
-- CMAKE_HOST_SYSTEM_NAME IS Windows
-- UNIX IS
-- WIN32 IS  1
-- CMAKE_C_COMPILER_ID IS  MSVC
-- CMAKE_CXX_COMPILER_ID IS  MSVC
-- CMAKE_C_COMPILER_VERSION IS  19.28.29914.0
-- CMAKE_CXX_COMPILER_VERSION IS  19.28.29914.0
-- CMAKE_C_COMPILER IS  C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.28.29910/bin/Hostx64/x64/cl.exe
-- CMAKE_CXX_COMPILER IS  C:/Program Files (x86)/Microsoft Visual Studio/2019/Community/VC/Tools/MSVC/14.28.29910/bin/Hostx64/x64/cl.exe
-- CMAKE_C_COMPILER_LOADED IS  1
-- CMAKE_CXX_COMPILER_LOADED IS  1
```
