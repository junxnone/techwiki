---
Title | Shell read file
-- | --
Create Date | `2021-09-22T07:47:33Z`
Update Date | `2021-09-22T07:47:33Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/133)

---
# Reference
- [SHELL读取文件的方法](https://www.cnblogs.com/kongzhongqijing/articles/5101752.html)

# brief
- 使用 `while` 循环读取行

## 使用 `while` 循环读取行

```
while read myline
do
echo "LINE:"$myline
done < datafile.txt
```

- **如果文件最后一行之后没有换行符\n，则read读取最后一行时遇到文件结束符EOF，循环即终止。**
通过测试$line是否有内容来进行继续处理, 如下可解决此问题：

```
while read myline || [[ -n ${myline} ]]
```
> wc -l 统计 文件行数时也会遇到此问题，此时会出现错误 `统计行数-1`
>> 在 训练 YOLO 统计分类个数时踩坑一次
