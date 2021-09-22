---
Title | Shell Examples
-- | --
Create Date | `2019-05-21T22:46:11Z`
Update Date | `2021-09-22T02:44:19Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/76)

---
# Reference
- [linux shell 时间运算以及时间差计算方法](https://mp.weixin.qq.com/s/7QnycDf_D7jZJUGrdhrZ5w)

# Examples

## 逐行读取文件获取video 文件名，并统计视频帧数

```
#!/bin/bash
while read myline
do
    echo -n $myline
    echo -n ' | '
    mediainfo -f $myline|grep 'Color space' -B10|grep 'Frame count' |awk -F ':' '{print $2}'
done < filelist.txt
```

## 统计子目录各有多少文件

```
#!/bin/bash
while read myline
do
    echo -n $myline
    echo -n ' | '
    ls $myline |wc -l
done < $1

```

```
ls */* -d |xargs -i sh -c 'echo {};ls {}|wc -l'|xargs -n 2
```

## 时间运算以及时间差计算

- **获取时间戳**
 
```
time1=$(date +%s -d '1990-01-01 01:01:01')
```
>  %s   seconds since 1970-01-01 00:00:00 UTC
>   -d, --date=STRING          display time described by STRING, not 'now'

- **获取两天5小时后的时间**
- 
```
$ date
Mon May  4 23:55:18 CST 2020

$ time1=$(date +%s)
$ echo $time1
1588607562

$ time2=$((24*60*60*2+60*60*5))
$ echo $time2
190800

$ time3=$((time1+time2))
$ echo $time3
1588798362

$ time4=$(date +%Y-%m-%d\ %H:%M:%S -d "1970-01-01 UTC $time3 seconds")
$ echo $time4
2020-05-07 04:52:42
```

- **计算两个时间时间差(天数)**

```
$ time1=$((($(date +%s) - $(date +%s -d '2013-07-25'))/3600/24))
$ echo $time1
2476
```
> /3600 - 小时数
> /3600/24 - 天数



