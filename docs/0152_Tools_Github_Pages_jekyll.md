---
Title | Tools Github Pages jekyll
-- | --
Created @ | `2019-03-02T10:47:21Z`
Last Modify @| `2022-12-22T07:02:05Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/152)

---

# Reference
- [免费顶级域名+github个人主页教程](https://blog.csdn.net/lyp_hy/article/details/82116255)
- [参考wiki](https://ctf-wiki.github.io/ctf-wiki/)
- [Mirror - 基于 issues 的博客工具](https://mirror.am0200.com/#/posts/11)
  - [Mirror ](https://github.com/LoeiFy/Mirror)
- [python-github-backup](https://github.com/josegonzalez/python-github-backup)
- [域名注册](www.freenom.com)
- [Managing a custom domain for your GitHub Pages site](https://help.github.com/en/articles/managing-a-custom-domain-for-your-github-pages-site)
- [export issues to md](https://github.com/yanyue404/github-export)

# 设置 github io page
1. 新建 repo : xxx.github.io
2. 新建Readme.md
3. 选择theme
## 设置title/description/google analytics


# domain
## 设置Custom domain
```
www.xxx.xx
```
> 如果不添加www，解析会错误. why?



Name | Type | TTL | Target 
-- | -- | -- | -- 
 www | CNAME |  3600 |  xxx.github.io
空 | A | 3600 | 185.199.109.153

## 可以设置短网址跳转 URL Forwarding

- **URL Redirect**: When you use this forwarding type, a person typing your domain on the  browser (for example: www.yourdomain.com) gets redirected to the actual  web server where your web pages are hosted on (for  example:home.yourwebserver.com/yourdomain). However, after the  redirection, the browser's address bar will display the location of the  actual web page (home.yourwebserver.com/yourdomain) instead of  your domain name (www.yourdomain.com).
- **URL Frame**: This works similar to URL redirect type except that instead of redirecting the visitor to your web page, the web page is displayed in a frame from the server. The difference is that after redirection, the browser's address bar will continue to display your domain name (for example: www.yourdomain.com) in the browser's address bar instead of the actual location of the webpage.

# Jekyll plugins
