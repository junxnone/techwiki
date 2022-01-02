---
Title | cmake platforms
-- | --
Create Date | `2022-01-02T06:35:43Z`
Update Date | `2022-01-02T06:35:43Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/243)

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


Platform Variables | Description
-- | --
`UNIX` |  is TRUE on all UNIX-like OS's, including Apple OS X and *CygWin*
`WIN32` | is TRUE on Windows. Prior to 2.8.4 this included *CygWin*
`APPLE` | is TRUE on Apple systems. Note this does *not* imply the system is Mac OS X, only that **APPLE** is #defined in C/C++ header files.
`MINGW` | is TRUE when using the MinGW compiler in Windows
`MSYS` | is TRUE when using the MSYS developer environment in Windows
`CYGWIN` | is TRUE on Windows when using the *CygWin* version of cmake


CMake System name | Environments Where Seen
-------|-------------------------
`Windows` | Windows (Visual Studio, MinGW GCC) 
`Darwin` | macOS/OS X (Clang, GCC) 
`Linux` | Linux (GCC, Intel, PGI) 
`Android` | Android NDK (GCC, Clang) 
`FreeBSD` | FreeBSD 
`CrayLinuxEnvironment` | Cray supercomputers (Cray compiler) 
`MSYS` | Windows (MSYS2 shell native GCC) 
