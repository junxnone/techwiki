---
Title | Github Pages timeline markline
-- | --
Create Date | `2021-02-07T11:41:15Z`
Update Date | `2021-09-22T09:15:20Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/148)

---
# Reference
- [code](https://github.com/hotoo/markline)

# Brief

## ~~Install~~

> 可以不用安装, 直接使用 [template](https://github.com/hotoo/markline/tree/master/template)
```
sudo apt install npm
npm install markline -g
```

## Deploy

Num | Steps | Description
-- | -- | --
1 | Create Repo | 创建相关仓库
2 | 设置 Repo |  Settings 设置 Github Pages 对应的branch
3 | Copy 相关文件 |  `assets`  & `index.html`
4 | 创建 markdown |参考 [Format](https://github.com/hotoo/life/blob/gh-pages/hotoo.md)
5 | 更改 `index.html` 部分内容  |  `{FILE_NANE}` ==> `your_markdown`


![image](https://user-images.githubusercontent.com/2216970/107148151-b94b7480-698c-11eb-8af9-6b5d084af4da.png) | ![image](https://user-images.githubusercontent.com/2216970/107148102-640f6300-698c-11eb-8ba4-067db21d368a.png)
-- | --

## Support Features
- 粗体
- 时间线内隐藏时间点或时间段
- Tags
- 可以一个仓库创建多条 `timeline web`, 参考 [这里](https://github.com/junxnone/ht)

> 格式可以参考  [这里](https://github.com/junxnone/template_ht_markline)
