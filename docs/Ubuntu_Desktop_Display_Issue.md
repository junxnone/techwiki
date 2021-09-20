---
Title | Ubuntu Desktop Display Issue
-- | --
Create Date | `2021-09-20T13:01:01Z`
Update Date | `2021-09-20T13:01:01Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/52)

---
## Reference
- [ubuntu桌面不显示（不完整）UI界面](https://blog.csdn.net/m0_37962554/article/details/79336744)

# Issue Ubuntu 桌面不显示

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
