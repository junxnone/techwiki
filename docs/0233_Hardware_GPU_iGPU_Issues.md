---
Title | Hardware GPU iGPU Issues
-- | --
Created @ | `2021-12-13T11:35:28Z`
Last Modify @| `2022-12-22T03:25:03Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/233)

---


### Ubuntu Cannot Access iGPU

- 非 root 用户无法访问 iGPU

```
sudo usermod -aG video $UserName
```
