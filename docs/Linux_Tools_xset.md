---
Title | Linux Tools xset
-- | --
Create Date | `2021-10-21T08:02:21Z`
Update Date | `2021-10-21T16:12:18Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/187)

---
# Brief
-  用于设置显示选项
- reboot 后重置

# UseCase

Usecase | cmd
-- | --
显示配置信息 | `xset q`
关闭屏保 | `xset s 0`
关闭 standby | `xset -dpms`<br>`xset dpms 0 0 0`
强制进入休眠 | `xset -display :0.0 dpms force off`
强制退出休眠 | `xset -display :0.0 dpms force on`
