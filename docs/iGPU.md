---
Title | iGPU
-- | --
Create Date | `2021-11-10T17:21:22Z`
Update Date | `2021-11-10T17:21:22Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/212)

---



## Ubuntu Access iGPU

- 非 root 用户无法访问 iGPU

```
sudo usermod -a -G video $UserName
```
