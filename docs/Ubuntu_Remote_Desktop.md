---
Title | Ubuntu Remote Desktop
-- | --
Create Date | `2021-01-06T03:05:58Z`
Update Date | `2021-10-26T09:07:32Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/11)

---
# Reference
- [Issues with xRDP and Ubuntu 18.04.2 – How to fix it](http://c-nergy.be/blog/?p=13390)
- [配置 VNC](https://www.mobibrw.com/2019/19379)
- [xRDP Installation Script](https://c-nergy.be/repository.html)
- [realvnc](https://www.realvnc.com/en/connect/download/viewer/)
- [TightVNC](https://www.tightvnc.com/download-old.php)


# Brief
- xrdp 方式 windows 访问 Linux
- [VNC](/VNC) 通用方式访问
- [vncserver](./vncserver)

# xrdp

- 安装 xrdp

```
wget http://www.c-nergy.be/downloads/Std-Xrdp-Install-0.5.3.zip
unzip Std-Xrdp-Install-0.5.3.zip
sudo chmod +x Std-Xrdp-Install-0.5.3.sh
./Std-Xrdp-Install-0.5.3.sh
```

> 0.5.3 only working with Ubuntu 18.04, Download the [New Version](https://c-nergy.be/repository.html)

- 卸载 xrdp

```
sudo apt purge xrdp
```

- host 端登录后不能识别 USB 鼠标键盘
`sudo -E apt-get install xserver-xorg-input-all`
> reboot after install the package, then the keyboard & mouse are back

# VNC

```
sudo apt-get update
sudo apt install lightdm
sudo apt install xserver-xorg-video-dummy xorg-video-abi-23 xserver-xorg-core
sudo reboot
sudo apt-get install x11vnc net-tools
sudo x11vnc -storepasswd /etc/x11vnc.pass
sudo chmod 755 /etc/x11vnc.pass
sudo x11vnc -auth guess -rfbauth /etc/x11vnc.pass -rfbport 5900 -forever -display :0
```
- **配置 systemd 开机启动**

```
sudo vim /etc/systemd/system/x11vnc.service
```
```
[Unit]
Description=x11vnc (Remote access)
After=network-online.target
 
[Service]
Type=simple
ExecStart=/usr/bin/x11vnc -auth guess -rfbauth /etc/x11vnc.pass -rfbport 5900 -forever -display :0
ExecStop=/bin/kill -TERM $MAINPID
ExecReload=/bin/kill -HUP $MAINPID
KillMode=control-group
Restart=on-failure
 
[Install]
WantedBy=graphical.target
```
```
sudo systemctl daemon-reload
sudo systemctl enable x11vnc
sudo systemctl start x11vnc
```



