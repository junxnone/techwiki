---
Title | Linux Vi UseCase
-- | --
Created @ | `2020-06-06T08:04:47Z`
Last Modify @| `2022-12-18T06:00:34Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/16)

---
# Reference
- [vim基础命令，查找和替换](https://www.cnblogs.com/woshimrf/p/vim.html)

## 简单使用

## 替换

命令 | Description
-- | --
`:s/old/new` | 用new替换行中首次出现的old
`:s/old/new/g` | 用new替换行中所有的old
`:n,m s/old/new/g` | 用new替换从n到m行里所有的old
`:%s/old/new/g` | 用new替换当前文件里所有的old

## 注释

**多行注释**：
1. 命令行模式 --> <kbd>ctrl + v</kbd> --> `visual block` 模式
2. <kbd>jk</kbd>, 选中需要注释的行
2. 大写字母<kbd>I</kbd>，插入注释符，例如 `//` 或 `#`
3. <kbd>esc</kbd>退出即可注释

**取消多行注释**：
1. 命令行模式 --> <kbd>ctrl + v</kbd> --> `visual block` 模式，
2. <kbd>hl</kbd>选中列数，<kbd>jk</kbd>选中行数
3. <kbd>d</kbd>取消注释

## Tips
Tips | cmd
-- | --
paste 多行 出现缩进 | `:set paste`
设置鼠标粘贴 | `：set mouse-=a`
设置隐藏字符可见 | `: set list`/`: set nolist`
设置终端背景色 [终端相关] | `编辑->配置文件首选项->配置文件->编辑->颜色`
