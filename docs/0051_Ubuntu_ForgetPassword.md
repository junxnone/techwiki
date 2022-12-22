---
Title | Ubuntu ForgetPassword
-- | --
Created @ | `2018-10-09T02:41:08Z`
Last Modify @| `2022-12-22T07:45:30Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/51)

---
# Reference
- [Ubuntu 16.04 重置密码（忘记密码）](https://blog.csdn.net/m0_37887449/article/details/73086882)

# Issue Description

> 过了个国庆假期，密码忘了，什么鬼......

## Steps
1. Reboot
2. 跳过 BIOS 时按下一次 "ESC" ，进入 BOOT 选项模式
3. 进入 Advanced Options for Ubuntu
4. 按 ↑ ↓选择内核最高版本的 recovery mode后按 “e”
5. 将引导内容 “ro recovery nomodeset” 改为 “rw single init=/bin/bash”
6. 按 “Ctrl+x” 引导进入系统
7. passwd yourname，输入两次新密码，修改成功
8. 长按开机键重启


