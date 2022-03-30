---
Title | Git
-- | --
Create Date | `2018-12-14T07:40:51Z`
Update Date | `2022-03-30T08:35:48Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/62)

---
## Reference
- [Git内部原理介绍](https://cloud.tencent.com/developer/article/1369947)
- [git-tips](https://github.com/jaywcjlove/git-tips)

## Brief

- [Git config](/Git_config)
- [Git proxy](/Git_proxy_config)
- [Git submodule](/Git_submodule)
- [Git branch](/Git_branch)
- [Git Tag](/Git_tag)
- [Git pre-commit](/Git_precommit)
- [Git archive](/Git_archive)


## Issues
- [Git 移除 stage 错误添加的文件](/Git_remove_file_from_stage)
- [No newline at end of file](/git_diff_no_newline_at_end_of_file)

## TODO

- 简单使用
  - commit
  - push
  - pull
  - tag
  - remote url
  - revert
  - stage
- 配置选项
  - name/email/编辑器
  - ssh key
  - proxy
- 子模块
- 内部原理

## gitlab 手动迁移到 github 
- 默认添加 remote --> push 只会 迁移 default branch

### 迁移所有分支
- 添加 remote

```
git remote add github_remote xxxxxx
```
- checkout 所有分支
```
 git branch -a |grep remote | grep -v master | awk -F '/' '{print "git checkout "$3}'|bash
```
- push
```
git push github_remote
```
### 迁移所有 tag
```
git tag|awk '{print "git push github_remote "$1}'|bash
```
