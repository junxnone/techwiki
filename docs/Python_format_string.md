---
Title | Python format string
-- | --
Create Date | `2019-07-19T04:41:16Z`
Update Date | `2022-03-28T06:56:40Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/255)

---
## Reference
- [python format() 格式化 数字](https://my.oschina.net/zhiyonghe/blog/1596271)
- [python f-string](https://www.cnblogs.com/c-x-a/p/9333826.html)

## Brief

```
print('The format is {:.2f}'.format(float_value))
print(f'Format string is {value:.2f}')
```




数字 | 格式 | 输出 | 描述
-- | -- | -- | --
3.1415926 | {:.2f} | 3.14 | 保留小数点后两位
3.1415926 | {:+.2f} | +3.14 | 带符号保留小数点后两位
-1 | {:+.2f} | -1.00 | 带符号保留小数点后两位
2.71828 | {:.0f} | 3 | 不带小数
5 | {:0>2d} | 05 | 数字补零 (填充左边, 宽度为2)
5 | {:x<4d} | 5xxx | 数字补x (填充右边, 宽度为4)
10 | {:x<4d} | 10xx | 数字补x (填充右边, 宽度为4)
1000000 | {:,} | 1,000,000 | 以逗号分隔的数字格式
0.25 | {:.2%} | 25.00% | 百分比格式
1000000000 | {:.2e} | 1.00e+09 | 指数记法
13 | {:10d} | 13 | 右对齐 (默认, 宽度为10)
13 | {:<10d} | 13 | 左对齐 (宽度为10)
13 | {:^10d} | 13 | 中间对齐 (宽度为10)
11 | '{:b}'.format(11)<br> '{:d}'.format(11)<br> '{:o}'.format(11)<br> '{:x}'.format(11)<br> '{:#x}'.format(11)<br> '{:#X}'.format(11) | 1011<br> 11<br> 13<br> b<br> 0xb<br> 0XB | 进制

## UseCase

UseCase | Implement
-- | --
数字不足左边补零 | `str('150').zfill(4)`
↑ | `'{:04d}'.format(150)`

## History

方法 | 引入时间 | 用法 | 优缺点
-- | -- | -- | --
%-formatting | 原生 | "Hello, %s. You are %s." % (name, age) | 多变量不易读
str.format() | python 2.6 | "Hello, {}. You are {}.".format(name, age) | 同上
f-strings | python 3.6 | f"Hello, {name}. You are {age}." | 速度更快

- f-strings 使用 `冒号 :` 分割格式化字符, 前面为替换变量，后面为格式化字符

