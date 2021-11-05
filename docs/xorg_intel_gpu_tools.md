---
Title | xorg-intel-gpu-tools
-- | --
Create Date | `2018-09-28T06:21:47Z`
Update Date | `2021-11-05T06:59:17Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/95)

---
# Reference 
- [xorg-intel-gpu-tools](https://github.com/freedesktop/xorg-intel-gpu-tools)

# Brief

## Install
### Install on ubuntu 16.04

- **Dependence Install**

```
sudo apt install -y libprocps-dev libkmod-dev libunwind-dev libdw-dev libudev-dev liboping-dev libjson-c-dev
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
