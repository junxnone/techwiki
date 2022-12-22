---
Title | Doc Markdown Image
-- | --
Created @ | `2021-09-22T10:09:29Z`
Last Modify @| `2022-12-22T07:18:28Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/163)

---

## Brief
- html label 控制图片显示不同比例
  - pixel 控制(`300px/100px/50`, 可以不加 px)
  - 百分比控制(`50%/20%/10%`)
  - 只定义一个参数 (width & height), 则同比例缩放
- **格式** `<img width="w px/%" height="h px/%" src="your_image_url">`


## 显示为不同比例的图片

- **50%  width & height**
  - ```<img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="50%" height="50%">```

- **300px with width**
  - ```<img width="300px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif">```


50% | <img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="50%" height="50%">
-- | --
10% | <img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="10%" height="10%">
300px | <img width="300px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif">

