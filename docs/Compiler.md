---
Title | Compiler
-- | --
Create Date | `2021-06-01T07:22:07Z`
Update Date | `2021-10-28T07:44:34Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/169)

---
# Reference
- [GCC](https://gcc.gnu.org/)
- [LLVM](https://llvm.org/)
- [ICC](https://software.intel.com/content/www/us/en/develop/documentation/cpp-compiler-developer-guide-and-reference/top.html)

# Brief
- Compiler - 编译器 - `将编程语言解释为处理器可执行指令`


Name | Description | OS 
-- | -- | --
[GCC](/GCC) | GNU Compiler Collection - 开源软件常用的编译器 | Linux
MSVC | 微软开发的编译器 | Windows
[ICC](/Intel_Compiler) | Intel C++ Compiler Hardware 优化 | Linux/Windows
Clang | LLVM - Low Level Virtual Machine 编译器  | OS X
BCC | Borland C++ 退出历史？？？

- **LLVM Project** is a collection of modular and reusable compiler and toolchain technologies

# Steps

Name | Inputs | Outputs | GCC | ICC
-- | -- | -- | -- | -- 
预处理器 | 源代码 | 预处理的代码
编译器 | ↑ | 汇编代码 | gcc/g++ | icl/icx/icc/icpc/icpx
汇编器 | ↑ | 可重定位的机器代码 | as |
链接器 | 库文件 + ↑ | 目标机器代码


# Tools 

Name | Description
-- | --
AR | 库管理器
OBJDUMP |
RANLIB |

