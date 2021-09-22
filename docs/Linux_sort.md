---
Title | Linux sort
-- | --
Create Date | `2021-09-22T01:55:14Z`
Update Date | `2021-09-22T01:55:14Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/73)

---
# Brief

- **`sort` 常用参数**

```
  -b   忽略每行前面开始出的空格字符。
  -c   检查文件是否已经按照顺序排序。
  -f   排序时，忽略大小写字母。
  -M   将前面3个字母依照月份的缩写进行排序。
  -n   依照数值的大小排序。
  -o<输出文件>   将排序后的结果存入指定的文件。
  -r   以相反的顺序来排序。
  -t<分隔字符>   指定排序时所用的栏位分隔字符。
  -k  选择以哪个区间进行排序。
```

# UseCase
- **去重复**

当 ids.txt 里面包含较多重复的行时，可以使用 `sort -u` 去重复

```
cat ids.txt|sort -u 
```
>sort 参数：   
-u, --unique  with -c, check for strict ordering; without -c, output only the first of an equal run

