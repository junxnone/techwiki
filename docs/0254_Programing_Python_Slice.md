---
Title | Programing Python Slice
-- | --
Created @ | `2019-05-14T14:34:29Z`
Last Modify @| `2022-12-22T06:31:03Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/254)

---
## Reference
- [python切片操作](https://www.cnblogs.com/mzct123/p/6031092.html)
- [Understanding slice notation](https://stackoverflow.com/questions/509211/understanding-slice-notation)


## Brief

- slice 切片


Pattern | Description | UseCase
-- | -- | --
**seq**[`s_index`:`e_index`] | 从 `s_index` 到 `e_index -1` 的切片 | `s  == s[:]`
**seq**[`s_index`:`e_index`:`step`] | 从 `s_index` 到 `e_index -1` 的切片, 每隔 `step` 取一次值 | `s[-2:-6:-1]`






## UseCase

UseCase | Example | Description
-- | -- | --
多维(矩阵) | `a[1:2, 2:3]` | 取第一维的`[2-3)`和第二维的`[3-5)`
翻转字符串 `::` | `a[::-1]` == `a[-1:-len(a)-1:-1]`| `s_index` & `e_index` 不指定 `step=-1`
省略号 `…` | `a[:, :, None]` == `a[…, None]` | 省略其他维度
Image BGR->RGB | channels first `img = img[::-1, ...]` <br>channles last `img = img[..., ::-1]` == `img[:, :, ::-1]`



```
s[-2:-6:-1]
```
![image](https://user-images.githubusercontent.com/2216970/57706766-f2ac5e80-7698-11e9-9cd9-9c93ac14ab86.png)
![image](https://user-images.githubusercontent.com/2216970/57706721-e32d1580-7698-11e9-947c-0d6822597a9b.png)

> 不包括ending_index



