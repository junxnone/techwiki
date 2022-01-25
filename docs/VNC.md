---
Title | VNC
-- | --
Create Date | `2021-10-26T09:06:55Z`
Update Date | `2022-01-25T11:15:42Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/191)

---
## Reference

- [vnc简介](https://github.com/levinit/itnotes/blob/main/vnc.md)
- [Virtual Network Computing - wikipedia](https://en.wikipedia.org/wiki/Virtual_Network_Computing)
- [RFB protocol](https://en.wikipedia.org/wiki/RFB_protocol)


## Brief
- VNC - Virtual Network Computing/Virtual Network Console - 图形桌面共享系统
- VNC 由AT&T 的剑桥研究实验室开发，可实现远程图像显示和控制。
- Tools
  - TightVNC
  - TigerVNC
  - TurboVNC
  - RemoteVNC
  - RealVNC
  - vino/vinagre
  - x11vnc
- RFB protocol - `remote framebuffer protocol`


## UseCase

Usecase | cmd
-- | --
启动 vncserver |  `vncserver :1 -geometry 1920x1080 -depth 24`
查看 启动的 server | `ps -ef \|grep vnc`
kill server | `vncserver -kill :1`

## Issues
### 显示复选框
![image](https://user-images.githubusercontent.com/2216970/150967111-67938d74-01b2-4277-a7fd-27065891ede2.png)


