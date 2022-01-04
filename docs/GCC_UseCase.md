---
Title | GCC UseCase
-- | --
Create Date | `2022-01-04T09:21:20Z`
Update Date | `2022-01-04T10:12:09Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/245)

---
## Brief

## UseCase

UseCase | Command
-- | --
执行到预编译 | `gcc -E demo.c`
执行到汇编 | `gcc -S demo.c`
执行到目标文件 | `gcc -C demo.c`

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


