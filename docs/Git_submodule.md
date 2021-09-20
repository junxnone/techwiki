---
Title | Git submodule
-- | --
Create Date | `2021-09-20T13:38:08Z`
Update Date | `2021-09-20T13:38:08Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/58)

---

# Brief
- git 包含嵌套的概念, 仓库中可以包含另一个仓库

## 新建包含子仓库的仓库

```
cd workdir
git init
git submodule add https://xxxx.git subdir
```

## update 所有仓库

```
git submodule update --init --recursive
```

## Git 更改submodule 的地址


分别更改如下文件中的子模块地址
- .submodule
- .git/config


> 在运行 git submodule update --init --recursive 时，.submodule 中的 submodule 会更新到.git/config 中，所以运行此命令之前可以只更新.submodule 文件
