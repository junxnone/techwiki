---
Title | Markdown Image
-- | --
Create Date | `2021-09-22T10:09:29Z`
Update Date | `2022-01-19T06:50:05Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/163)

---
- 使用 html label 控制 图片缩放 `pixel` 或者比例
- 也可以直接使用 size ` width="500" height="500"`

```
<img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="50%" height="50%">
```
```
<img width="300px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif">
```

## 显示为不同比例的图片

- **50%  width & height**
  - ```<img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="50%" height="50%">```

- **300px with width**
  - ```<img width="300px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif">```


50% | <img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="50%" height="50%">
-- | --
10% | <img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="10%" height="10%">
300px | <img width="300px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif">

