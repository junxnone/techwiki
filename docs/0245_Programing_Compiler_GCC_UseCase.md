---
Title | Programing Compiler GCC UseCase
-- | --
Created @ | `2022-01-04T09:21:20Z`
Last Modify @| `2022-12-22T03:35:38Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/245)

---
## Brief

## UseCase

UseCase | Command
-- | --
执行到预编译 | `gcc -E demo.c`
执行到汇编 | `gcc -S demo.c`
执行到目标文件 | `gcc -C demo.c`
生成可调试的版本 | `gcc -g demo.c`
开启警告信息 | `gcc -Wall demo.c`
链接库 `libxxx.a` 并包含头文件 | `gcc demo.c -L/path/to/lib -lxxx -I/path/to/include` 


### 架构相关
- `-march`

### 优化相关

Option | Description
-- | --
`-O0` | 不优化
`-O1` | 优化，最小化编译时间
`-O2` | more costly optimizations
`-O3` | `auto inlining`/`vectorizer`
`-Os` | 优化代码大小

### Others
- `-fPIC` - `Position-Independent Code` - 产生与位置无关代码
  - 使用相对地址
