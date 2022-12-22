---
Title | Tools Gitlab
-- | --
Created @ | `2019-09-06T06:19:17Z`
Last Modify @| `2022-12-22T07:06:14Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/132)

---

## Reference

## Brief
- [CICD](./Gitlab_CICD)

## Issues

### **Issue 1 新建了仓库，但是不能push 到 master**

>  master 分支 设置了protect，不能直接push，需要先 push到新分支，然后再 merge 到 master

### **Issue 2 新建了仓库，不能push到 新的dev 分支**

> 需要 owner 或者maintainer 创建 master 分支之后，developer 才能 push 并新建分支

```
git branch dev
git push origin dev
```
