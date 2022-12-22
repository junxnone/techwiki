---
Title | Pandas Series
-- | --
Created @ | `2019-08-14T05:12:21Z`
Last Modify @| `2022-12-22T08:16:43Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/280)

---
## Reference
- [API Docs](https://pandas.pydata.org/pandas-docs/stable/reference/series.html)

## Brief
- Series是带有标签的一维数组，可以保存任何数据类型（整数，字符串，浮点数，Python对象等）


## 创建Series
- 可用的初始化数据类型
  - Python dict（字典）
  - ndarray
  - 标量值

```
pd.Series(data, index=index)
```

### 字典 dict 初始化

- 如果传入了index，则会取出数据中的值，对应于索引中的标签。
```
d = {'a' : 0., 'b' : 1., 'c' : 2.}
pd.Series(d)

a    0.0
b    1.0
c    2.0
```

- 如果没有传递索引，将从字典的有序键构造索引
```
pd.Series(d, index=['b', 'c', 'd', 'a'])

b    1.0
c    2.0
d    NaN
a    0.0
```

### ndarray 初始化
- 如果没有传递索引，将创建值为[0， ...， len(data) - 1]的索引
```
pd.Series(np.random.randn(5))

0    0.3674
1   -0.8230
2   -1.0295
3   -1.0523
4   -0.8502
```
- 传递的索引必须与数据长度相同
```
s = pd.Series(np.random.randn(5), index=['a', 'b', 'c', 'd', 'e'])

a    0.2735
b    0.6052
c   -0.1692
d    1.8298
e    0.5432
```

### 标量 初始化
- data是标量值，则必须提供索引。该值会重复，来匹配索引的长度
```
pd.Series(5., index=['a', 'b', 'c', 'd', 'e'])

a    5.0
b    5.0
c    5.0
d    5.0
e    5.0
```

## 访问 & 操作
### numpy式访问 & 切片
```
s[0]
s[:3]
s[s > s.median()]
s[[4, 3, 1]]
np.exp(s)
s + s
s * 2
s[1:] + s[:-1]
```
> Series 和 ndarray 之间的主要区别是，Series 上的操作会根据标签自动对齐数据

### 使用标签作为索引来获取和设置值
```
s['a']
s['e'] = 12

'e' in s
True / False
s.get('f')
s.get('f', np.nan)
nan
```



