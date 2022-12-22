---
Title | X CRLF
-- | --
Created @ | `2020-04-23T09:44:34Z`
Last Modify @| `2022-12-22T07:22:45Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/34)

---
## Reference
- [tofrodos - ubuntu](http://manpages.ubuntu.com/manpages/focal/man1/fromdos.1.html)

## Brief

- CR - Carriage-Return - 回车 - `ASCII 13` - `\r`
- LF -  Line-Feed - 换行 -  `ASCII 10` - `\n`

OS | 换行符
-- | --
Windows | CRLF
Linux/Unix | LF
< Mac OS 9 | CR
\> Mac OS X | LF
 
## Tools

- tofrodos 

```
fromdos your_file
todos your_file
```

- dos2unix  - `CRLF --> LF`

```
dos2unix  your_file
```

- file - 检查是不是 `CRLF` format

```
file your_file
your_file: Bourne-Again shell script, ASCII text executable, with CRLF line terminators
```

- vim 

```
vim -b your_file
```

> `^M` 结尾 的为 `CRLF`

## History

打字机按键 | 行为
-- | --
LF  |  换行，但是列位置不变
CR | 不换行，回到纸张最左侧


