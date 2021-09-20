---
Title | Git remove file from stage
-- | --
Create Date | `2021-09-20T13:45:34Z`
Update Date | `2021-09-20T13:45:34Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/61)

---

- 使用 `git add file` ，发现添加错文件，从stage中移除文件

该文件不在repository内 | `git rm --cached filename`
-- | --
该文件已经在repository内 | `git reset HEAD filename`
