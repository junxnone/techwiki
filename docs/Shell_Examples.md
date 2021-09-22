---
Title | Shell Examples
-- | --
Create Date | `2019-05-21T22:46:11Z`
Update Date | `2021-09-22T02:16:58Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/76)

---
**逐行读取文件获取video 文件名，并统计视频帧数**

```
#!/bin/bash
while read myline
do
    echo -n $myline
    echo -n ' | '
    mediainfo -f $myline|grep 'Color space' -B10|grep 'Frame count' |awk -F ':' '{print $2}'
done < filelist.txt
```
