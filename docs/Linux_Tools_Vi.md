---
Title | Linux Tools Vi
-- | --
Created @ | `2019-03-07T07:38:27Z`
Last Modify @| `2022-12-18T06:00:50Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/14)

---
# Reference
- [vim-deprecated](https://github.com/ma6174/vim-deprecated)
- [安装 YouCompleteMe](https://www.cnblogs.com/feiyuhuo/p/10274236.html)

# Brief
- Install/Setup 
- [UseCase](./Vi_Usecase)
- [Plugins](./Vi_plugins)

## Install and Setup - 自动安装插件

### 1 使用自动化脚本获取插件并安装
  
```
wget -qO- https://raw.github.com/ma6174/vim/master/setup.sh | sh -x
```

### 2 设置侧边目录树 `Nerdtree - F3` 快捷键

-  添加 `map <F3> :silent! NERDTreeToggle<CR>` 到 `~/.vimrc`

>o  打开文件/目录
s  以新窗口形式打开文件
?  获取帮助

### 3 设置 `Tagbar - F4`  快捷键 - 查看 `tag[函数/变量]`   
 
- **3.1** [Download tagbar.vmb](http://www.vim.org/scripts/script.php?script_id=3465)
- **3.2** vim 编辑并执行命令
  - `vim tagbar.vba / tagbar.vmb` 
  - `:so%` 
  - `:q`
- **3.3** 添加 `map <F4>: TagbarToggle<CR>` 到 `~/.vimrc`:


