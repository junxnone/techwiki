---
Title | iGPU Issues
-- | --
Create Date | `2021-12-13T11:35:28Z`
Update Date | `2021-12-13T11:35:28Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/233)

---


### Ubuntu Cannot Access iGPU

- 非 root 用户无法访问 iGPU

```
sudo usermod -aG video $UserName
```
