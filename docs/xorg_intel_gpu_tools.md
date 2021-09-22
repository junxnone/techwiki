---
Title | xorg-intel-gpu-tools
-- | --
Create Date | `2021-09-22T05:53:46Z`
Update Date | `2021-09-22T05:53:46Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/95)

---

# Reference 
- [xorg-intel-gpu-tools](https://github.com/freedesktop/xorg-intel-gpu-tools)

# Brief

## Install
### Install on ubuntu 16.04

- **Dependence Install**

```
sudo apt install -y libprocps-dev libkmod-dev libunwind-dev libdw-dev libudev-dev
```

- **Build from source**

```
git clone https://github.com/freedesktop/xorg-intel-gpu-tools.git
cd xorg-intel-gpu-tools
./autogen.sh
make
sudo make install
```

## UseCase

```
sudo intel_gpu_top
```
```
intel-gpu-top -  300/ 300 MHz;   60% RC6;   0.15 Watts;       65 irqs/s

      IMC reads:     2177 MiB/s
     IMC writes:     2238 MiB/s

          ENGINE      BUSY                                                                                                                                                                  MI_SEMA MI_WAIT
     Render/3D/0     1.66% |██▌                                                                                                                                                           |      0%      0%
       Blitter/0     0.00% |                                                                                                                                                              |      0%      0%
         Video/0     0.00% |                                                                                                                                                              |      0%      0%
  VideoEnhance/0     0.00% |                                                                                                                                                              |      0%      0%
```
