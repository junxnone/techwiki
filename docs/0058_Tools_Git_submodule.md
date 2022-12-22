---
Title | Tools Git submodule
-- | --
Created @ | `2018-12-10T05:55:39Z`
Last Modify @| `2022-12-22T06:47:49Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/58)

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
