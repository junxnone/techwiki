---
Title | Shell comment
-- | --
Create Date | `2021-09-22T01:49:47Z`
Update Date | `2021-09-22T01:49:47Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/70)

---
# Reference
- [shell 脚本中的注释详解](https://www.cnblogs.com/dylancao/p/11797412.html)
- [shell 中长命令的换行处理](https://www.cnblogs.com/Wayou/p/line_break_for_long_shell_command.html)

# Brief

- 单行注释

```
# this is comment test
```

- 多行注释

```
:<<eof
this is comment
this is comment
this is comment
this is comment
eof
```
```
:<<!
this is comment
this is comment
this is comment
this is comment
!
```
```
: '
this is comment
this is comment
this is comment
this is comment
'
```

<kbd>:</kbd> & <kbd>'</kbd> 之间有空格

- shell script 中 `\` 换行的注释 \` # xxxx\`

```
python3 preprocess.py \
   `# -input filename`\
    -input filename\
    -input filename\
```
```
python3 preprocess.py \
    -input filename `# xxxx` \
    -input filename\
    -input filename\
```

