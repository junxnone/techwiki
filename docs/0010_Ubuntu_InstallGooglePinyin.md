---
Title | Ubuntu InstallGooglePinyin
-- | --
Created @ | `2019-09-23T06:39:22Z`
Last Modify @| `2022-12-22T07:41:26Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/10)

---
# Reference
- [Ubuntu 18.04 fcitx chinese input setup(google and sogou)](http://blog.zedyeung.com/2018/08/05/Ubuntu-18-04-fcitx-chinese-input-setup-google-and-sogou/)
- [ubuntu20.04 LTS安装谷歌拼音输入法](https://blog.csdn.net/kan2016/article/details/105735645/)


# Ubuntu 20.04

Steps | Commands
-- | --
1 | `sudo apt install -y fcitx`
2 | `im-config`<br> 选择 `fcitx`
3 | Logout and Login(or reboot OS)
4 | `sudo apt install -y fcitx-googlepinyin`
5 | `fcitx-config-gtk3`
6 | <kbd> + </kbd>
7 | unselect `Only show current language`
8 | search google pinyin & add
9 | <kbd> Ctrl </kbd> + <kbd> Space </kbd> 切换输入法

# Ubuntu 18.04
## Install

```
sudo apt install -y fcitx-bin
sudo apt install -y fcitx-googlepinyin
```

## Setup

Settings -> Region & Language -> Manage Installed Languages  
-> Install/Remove Languages [ select Chinese (simplified) / Chinese (traditional) ]   
-> Keyboard input method system [select  fcitx]   
-> Apply System wide  
-> logout and login(or restart the OS)
-> Fcitx Config Tool  
-> <kbd> + </kbd>  
-> unselect `Only show current language`  
-> search google pinyin  & add  

**现在可以愉快的输入中文了**



