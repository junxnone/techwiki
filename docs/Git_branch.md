---
Title | Git branch
-- | --
Create Date | `2019-03-25T11:02:40Z`
Update Date | `2022-01-10T06:39:37Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/60)

---
## Reference
- [成熟的 Git 分支模型](https://my.oschina.net/liebrother/blog/2990683)

## Brief

**分支介绍**
- master ：这个分支的代码是发布到生产的代码
- develop ：这个分支的代码是预发布到生产的代码
- release ：这个分支的代码是新版本发布到生产的代码
- feature ：这个分支的代码是新需求开发的代码
- hotfix(bugfix) ：这个分支的代码是紧急修复生产 bug 的代码

![image](https://user-images.githubusercontent.com/2216970/54083396-9e65c500-435d-11e9-9dee-ae52aa3447ce.png)

## UseCase

Usecase| 命令 
-- | --
新建 Branch  | `git branch dev`
列出当前 Branch | `git branch`
列出所有 Branch | `git branch -a`	
列出所有 Remote Branch | `git branch -r`
删除本地 Branch | `git branch -D branchname`
删除 Remote Branch | `git branch -r -d origin/branch-name`<br>`git push origin :branch-name`<br> `git push origin --delete branch_name`
合并 Branch 到 Master | `git checkout master`<br>`git merge dev`
Remote Branch 已删除<br>但 Local 仍能看到 | `git remote prune origin`
show all branch details | `git show-branch`
命令行显示分支路线| `git log --graph --all --oneline`
