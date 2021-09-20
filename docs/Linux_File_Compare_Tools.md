---
Title | Linux File Compare Tools
-- | --
Create Date | `2021-09-20T12:36:09Z`
Update Date | `2021-09-20T12:36:09Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/48)

---
# Tools
- meld
- diff
  - `grc diff`
  - `diff -u`
  - `diff --color`
- `vim -d`
-  vimdiff
- colordiff

# 文本文件比较
```
meld file1 file2
```
```
vim -d file1 file2
```
```
diff file1 file2
```

# 二进制文件比较
```
vim -bd file1 file2
```
