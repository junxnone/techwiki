---
Title | Tools yarn
-- | --
Created @ | `2019-03-02T06:29:43Z`
Last Modify @| `2022-12-22T08:10:12Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/127)

---

# Reference
- [Installation](https://yarnpkg.com/en/docs/install#debian-stable)
- [中文文档](https://yarn.bootcss.com/docs/)
- [yarn详细入门教程](https://blog.csdn.net/x550392236/article/details/79205812)

# Brief
> Yarn 是 Facebook, Google, Exponent 和 Tilde 开发的一款新的 JavaScript 包管理工具。

它的目的是解决这些团队使用 npm 面临的少数问题，即：
1. 安装的时候无法保证速度/一致性
2. 安全问题，因为 npm 安装时允许运行代码

## Install
```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn
```
## Setup
### yarn 使用国内镜像

```
yarn config set registry https://registry.npm.taobao.org
yarn config list
```
### yarn 代理
```
vi ~/.yarnrc
## add these lines to .yarnrc
env:
    proxy 'http://localhost:8118'
    https_proxy 'https://localhost:8118'
    strict-ssl false
```



