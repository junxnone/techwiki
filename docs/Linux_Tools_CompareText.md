---
Title | Linux Tools CompareText
-- | --
Created @ | `2018-10-17T06:58:59Z`
Last Modify @| `2022-12-20T09:03:31Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/48)

---
## Tools
- meld
- diff
  - `grc diff`
  - `diff -u`
  - `diff --color`
- `vim -d`
-  vimdiff
- colordiff

## 文本文件比较

```
meld file1 file2
```
```
vim -d file1 file2
```
```
diff file1 file2
```

## 二进制文件比较

```
vim -bd file1 file2
```
