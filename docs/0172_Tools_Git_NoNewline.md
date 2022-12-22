---
Title | Tools Git NoNewline
-- | --
Created @ | `2019-07-05T03:05:04Z`
Last Modify @| `2022-12-22T06:50:58Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/172)

---
# Reference
- [No Newline at End of File](https://thoughtbot.com/blog/no-newline-at-end-of-file)
- [How to add a newline to the end of a file?](https://unix.stackexchange.com/questions/31947/how-to-add-a-newline-to-the-end-of-a-file)

----

- **Issue** - `git diff \ No newline at end of file`
- when use `git diff somefile`, it says ` \ No newline at end of file` in the end

# Solution

Target | command
-- | --
查找 CRLF 结尾的文件 | `file * \| grep CRLF`
把文件从 `dos format` 转到 `unix format` | `dos2unix  your_file`
把所有文件转换格式 | `file *\|grep CRLF\|awk -F ":" '{print $1}'\|xargs -i dos2unix {}`
添加 `\n` | `sed -i -e '$a\'`

