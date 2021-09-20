---
Title | Git tag
-- | --
Create Date | `2021-09-20T13:54:26Z`
Update Date | `2021-09-20T13:54:26Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/63)

---

# UseCase

Usecase | cmd
-- | --
查看所有tag | `git tag`
查看匹配某些类型的标签 | `git tag -l 'v1.4.2.*'`
创建一个含附注类型的标签 | `git tag -a v1.4 -m 'my version 1.4'`
给某一个commit 打 tag | `git tag -a v1.2 9fceb02`
push 特定tag | `git push origin v1.5`
一次push所有本地新增的标签 | `git push origin --tags`
删除本地tag | `git tag -d v1.1`

> 默认情况下，git push 并不会把标签传送到远端服务器上，只有通过显式命令才能分享标签到远端仓库。

- 签名 Tag 
- 如果你有自己的私钥，还可以用 GPG 来签署标签，只需要把之前的 -a 改为 -s （译注： 取 signed 的首字母）即可：
```
git tag -s v1.5 -m 'my signed 1.5 tag'
```
- 验证 Tag
- 此命令会调用 GPG 来验证签名，所以你需要有签署者的公钥，存放在 keyring 中，才能验证
```
git tag -v v1.4.2.1
```


- **命令行删除远程tag**
> 待测试
```
git push origin :refs/tags/v1.1　　　　//先删除本地tag，再执行此命令，删除远程tag
```
