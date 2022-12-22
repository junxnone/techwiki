---
Title | Ubuntu Issues DesktopDisplay
-- | --
Created @ | `2018-11-06T06:43:33Z`
Last Modify @| `2022-12-22T07:48:06Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/52)

---

# 桌面不显示

## Reference
- [ubuntu桌面不显示（不完整）UI界面](https://blog.csdn.net/m0_37962554/article/details/79336744)


## Issue `1` description

1. 桌面不显示
2. 可以登录
3. 可以进入命令行，可以远程


### Solution

```
mv ~/.cache ~/.cache-NOGOOD
sudo reboot
```

## Issue `2` description

Ubuntu16.04 --> Ubuntu 18.04
升级后重启之后进入只有一张壁纸界面，不能输入。

### Solution

1.  <kbd>CTRL</kbd> +  <kbd>ALT</kbd> +  <kbd>F2</kbd> 进入命令行
2.  `startx`
3. Setup the desktop
