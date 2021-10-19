---
Title | Yocto Set Static IP
-- | --
Create Date | `2021-10-19T15:46:08Z`
Update Date | `2021-10-19T15:46:08Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/185)

---

# Reference
- [systemd-networkd  - Wired adapter using a static IP](https://wiki.archlinux.org/index.php/Systemd-networkd#Wired_adapter_using_a_static_IP)

# Brief
- Yocto 使用 systemd-networkd 来管理网络


```
# vi /etc/systemd/network/20-wired.network
```
```
[Match]
Name=enp1s0

[Network]
Address=10.1.10.9/24
Gateway=10.1.10.1
DNS=10.1.10.1
#DNS=8.8.8.8
```
