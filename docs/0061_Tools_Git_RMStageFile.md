---
Title | Tools Git RMStageFile
-- | --
Created @ | `2019-02-18T17:16:56Z`
Last Modify @| `2022-12-22T06:50:14Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/61)

---

- 使用 `git add file` ，发现添加错文件，从stage中移除文件

该文件不在repository内 | `git rm --cached filename`
-- | --
该文件已经在repository内 | `git reset HEAD filename`
