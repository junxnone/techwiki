---
Title | List Hardware info
-- | --
Created @ | `2019-02-20T04:32:30Z`
Last Modify @| `2022-12-21T10:22:38Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/7)

---
# Hardware 查看工具

## Reference
- [在Linux上查询物理机信息-不用去拆机器了](https://www.cnblogs.com/operationhome/p/12486702.html)

## Brief

command | description
-- | -- 
lshw | all hardware
dmidecode |  all hardware
lscpu | CPU
fdisk | Disk
smartctl | Disk
df  | Disk
lsblk | block Device
lspci | PCI Device
lsusb | usb Device
inxi |

## CPU
```
lscpu
```
```
cat /proc/cpuinfo
```
```
dmidecode --type processor
```

## BaseBoard
```
dmidecode --type baseboard|head 
```
- 支持的最大 `Memory`
```
sudo dmidecode |grep "Maximum Capacity" 
```
```
sudo  dmidecode --type memory |head 
```

## Memory
```
free -h
```
```
sudo dmidecode |grep -A 6 "Memory Device"
```
```
sudo dmidecode -t memory
```
- 查看 `单条内存大小`
```
sudo dmidecode --type memory |grep "Size"
```
- 查看 `内存型号`
```
dmidecode --type memory |grep "Part Number"
```
- 可以扩展内存条数目
```
dmidecode --type memory |grep "Number Of Devices"
```

## Disk
```
sudo fdisk -l|grep Disk
```
```
lsblk
```
```
df -h
```
```
sudo smartctl --all /dev/sda
```
```
sudo smartctl --all /dev/sda -d megaraid,N
```
> N is 0,1...


## PCI
```
lspci
```

## USB
```
lsusb
```

# inxi
```
inxi -F
System:    Host: xxxx Kernel: 4.15.0-64-generic x86_64 bits: 64 Console: tty 10
           Distro: Ubuntu 18.04.2 LTS
Machine:   Device: server System: Dell product: PowerEdge T630 serial: N/A
           Mobo: Dell model: 0NT78X v: A10 serial: N/A BIOS: Dell v: 2.8.0 date: 05/23/2018
CPU(s):    2 10 core Intel Xeon E5-2630 v4s (-MT-MCP-SMP-) cache: 51200 KB
           clock speeds: max: 3100 MHz 1: 1201 MHz 2: 1202 MHz 3: 1201 MHz 4: 1202 MHz 5: 1203 MHz 6: 1198 MHz
           7: 1200 MHz 8: 1199 MHz 9: 1201 MHz 10: 1198 MHz 11: 1201 MHz 12: 1205 MHz 13: 1204 MHz 14: 1199 MHz
           15: 1463 MHz 16: 1199 MHz 17: 1201 MHz 18: 1199 MHz 19: 1202 MHz 20: 1199 MHz 21: 1198 MHz
           22: 1198 MHz 23: 1200 MHz 24: 1198 MHz 25: 1198 MHz 26: 1199 MHz 27: 1200 MHz 28: 1198 MHz
           29: 1199 MHz 30: 1210 MHz 31: 1199 MHz 32: 1198 MHz 33: 1198 MHz 34: 1199 MHz 35: 1602 MHz
           36: 1198 MHz 37: 1198 MHz 38: 1198 MHz 39: 1198 MHz 40: 1199 MHz
Graphics:  Card-1: NVIDIA GP102 [GeForce GTX 1080 Ti]
           Card-2: NVIDIA GP102 [GeForce GTX 1080 Ti]
           Card-3: Matrox Systems G200eR2
           Card-4: NVIDIA GP102 [GeForce GTX 1080 Ti]
           Card-5: NVIDIA GP102 [GeForce GTX 1080 Ti]
           Display Server: N/A driver: (unloaded: nvidia) tty size: 189x49 Advanced Data: N/A out of X
Audio:     Card 4x NVIDIA GP102 HDMI Audio Controller
           driver: snd_hda_intelsnd_hda_intelsnd_hda_intelsnd_hda_intel
           Sound: Advanced Linux Sound Architecture v: k4.15.0-64-generic
Network:   Card-1: Intel I350 Gigabit Network Connection driver: igb
           IF: eno1 state: up speed: 1000 Mbps duplex: full mac: d0:94:66:67:16:0e
           Card-2: Intel I350 Gigabit Network Connection driver: igb
           IF: eno2 state: down mac: d0:94:66:67:16:0f
Drives:    HDD Total Size: 20402.9GB (51.5% used)
           ID-1: /dev/sdc model: SSDSC2KB960G8R size: 960.2GB
           ID-2: /dev/sde model: PERC_H330_Adp size: 479.6GB
           ID-3: /dev/sdd model: SSDSC2KB960G8R size: 960.2GB
           ID-4: /dev/sda model: ST8000NM0185 size: 8001.6GB
           ID-5: /dev/sdb model: ST8000NM0185 size: 8001.6GB
           ID-6: /dev/sdf model: PERC_H330_Adp size: 1999.8GB
Partition: ID-1: / size: 439G used: 281G (68%) fs: ext4 dev: /dev/sde2
RAID:      No RAID devices: /proc/mdstat, md_mod kernel module present
Sensors:   System Temperatures: cpu: 25.0C mobo: N/A
           Fan Speeds (in rpm): cpu: N/A
Info:      Processes: 590 Uptime: 7 days Memory: 10682.5/273860.6MB Init: systemd runlevel: 5
           Client: Shell (bash) inxi: 2.3.56
```
