---
Title | Docker UI
-- | --
Created @ | `2022-08-25T07:27:52Z`
Last Modify @| `2022-08-25T07:27:52Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/295)

---
## Reference
- [Docker容器显示图形到宿主机屏幕](https://blog.csdn.net/Frank_Abagnale/article/details/80243939)

## Brief
- **两种方式**: `网络方式` 和 `挂载方式`
- HOST 端安装有 Xserver
- 依赖
  - `sudo apt install x11-xserver-utils`
- 当前显示环境变量 `$DISPLAY`  - `echo $DISPLAY`
- 许可所有用户都可访问xserver - `xhost +`

### 挂载方式

- 创建时指定参数  (`:0` 为当前 $DISPLLAY`)
```
-v /tmp/.X11-unix:/tmp/.X11-unix
-e DISPLAY=:0
```


### 网络方式

- 配置允许 TCP 访问
```
sudo vim /etc/lightdm/lightdm.conf
[SeatDefaults]
xserver-allow-tcp=true
```
- 重启
- docker 内部变量 配置
```
export DISPLAY=xxx.xxx.xxx.xx:0
```

### 验证小工具

- xarclock - 时钟小工具

> 在 docker bash 中运行 xarclock, 可在当前 UI 显示时钟




