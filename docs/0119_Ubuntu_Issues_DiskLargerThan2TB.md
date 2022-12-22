---
Title | Ubuntu Issues DiskLargerThan2TB
-- | --
Created @ | `2019-04-30T08:32:25Z`
Last Modify @| `2022-12-22T07:52:12Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/119)

---
# 硬盘大于 2TB

## Reference
- [Ubuntu挂载3T硬盘或大于2T磁盘](https://blog.csdn.net/zhengchaooo/article/details/79500075)


## Brief
- MBR分区表不支持容量大于2.2TB（2.2 × 1012字节）的分区
-  使用 parted 建立 GPT 分区

```
$ sudo parted /dev/sda
GNU Parted 3.2
Using /dev/sda
Welcome to GNU Parted! Type 'help' to view a list of commands.

(parted) print
Error: /dev/sda: unrecognised disk label
Model: SEAGATE ST8000NM0185 (scsi)
Disk /dev/sda: 8002GB
Sector size (logical/physical): 512B/4096B
Partition Table: unknown
Disk Flags:

(parted) mklabel gpt

(parted) print
Model: SEAGATE ST8000NM0185 (scsi)
Disk /dev/sda: 8002GB
Sector size (logical/physical): 512B/4096B
Partition Table: gpt
Disk Flags:

Number  Start  End  Size  File system  Name  Flags

(parted) mkpart primary 0KB 8002GB
Warning: You requested a partition from 0.00B to 8002GB (sectors 0..15628053167).
The closest location we can manage is 17.4kB to 8002GB (sectors 34..15628053134).
Is this still acceptable to you?
Yes/No? YES

Warning: The resulting partition is not properly aligned for best performance.
Ignore/Cancel? Ignore

(parted) print
Model: SEAGATE ST8000NM0185 (scsi)
Disk /dev/sda: 8002GB
Sector size (logical/physical): 512B/4096B
Partition Table: gpt
Disk Flags:

Number  Start   End     Size    File system  Name     Flags
 1      17.4kB  8002GB  8002GB               primary

(parted) quit
Information: You may need to update /etc/fstab.

$ lsblk
NAME   MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sda      8:0    0   7.3T  0 disk
└─sda1   8:1    0   7.3T  0 part

```

## Format

```
mkfs.ext4 /dev/sda1
```
