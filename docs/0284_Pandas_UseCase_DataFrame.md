---
Title | Pandas UseCase DataFrame
-- | --
Created @ | `2019-08-15T11:05:16Z`
Last Modify @| `2022-12-22T08:18:26Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/284)

---
## 查看数据
### 查看顶部和尾部的数据

```
df.head()
df.head(10)
df.tail(3)
```

### 查看统计信息

```
df.index  -> 显示索引
df.columns  -> 获取列名
df.dtypes  -> 列具有不同的数据类型
df.describe() -> 显示数据的快速统计摘要
df.coef.value_counts() -> 查看 ’coef' 列的直方图化数
df.coef.value_counts(1) -> 查看 ’coef' 列的直方图化数，归一化为1，即比例
df.mean()  -> 进行描述性统计
df.mean(1) -> 在axis 1 上进行描述性统计
```
> 输入 `df.` + <kbd>TAB</kbd> 可以自动补全所有的列名以及公共属性。



## 列操作

### 选择列
- 通过 label 选择单列
```
df['id']  ->选择列 'id'
df.id  -> 同上
```

- 通过 `loc` 选择多列
```
df.loc[:,'id']  -> 同上
df.loc[:,['id', 'coef']]  -> 选择两列
```

操作 | 语法 | 结果
-- | -- | --
选择列 | df[col] | Series
按标签选择多列 | df[['name', 'label', 'year']] | DataFrame

### 添加新列

- 根据其他列创建新列

```
df['three'] = df['one'] * df['two']
df['flag'] = df['one'] > 2
df['foo'] = 'bar' # 自动扩充添加列
df['one_trunc'] = df['one'][:2]
```
- 使用字典添加新列

```
df = df.append(dict_a, ignore_index=True)
```

- 通过numpy array赋值
```
df.loc[:, 'coef'] = np.array([5] * len(df))
```

- 插入某列

```
df.insert(1, 'bar', df['one'])
```
```
   one   flag  foo  one_trunc
a  1.0  False  bar        1.0
b  2.0  False  bar        2.0
c  3.0   True  bar        NaN
d  NaN  False  bar        NaN

----after insert----

   one  bar   flag  foo  one_trunc
a  1.0  1.0  False  bar        1.0
b  2.0  2.0  False  bar        2.0
c  3.0  3.0   True  bar        NaN
d  NaN  NaN  False  bar        NaN
```

- assign 添加新列

```
(iris.assign(sepal_ratio = iris['SepalWidth'] / iris['SepalLength'])

   SepalLength  SepalWidth  PetalLength  PetalWidth         Name  sepal_ratio
0          5.1         3.5          1.4         0.2  Iris-setosa       0.6863
1          4.9         3.0          1.4         0.2  Iris-setosa       0.6122
2          4.7         3.2          1.3         0.2  Iris-setosa       0.6809
3          4.6         3.1          1.5         0.2  Iris-setosa       0.6739
4          5.0         3.6          1.4         0.2  Iris-setosa       0.7200


# 传递函数，效果同上
iris.assign(sepal_ratio = lambda x: (x['SepalWidth'] / x['SepalLength'])).head() 

```

- 从一列的字符串中分离出部分字符成为新的一列
```
df['category'] = df['name'].str.split('_',1).str[0]
```
> 假设 df['name'] 为类似字符 `Class1_0000xxx.png`


### 删除列

- drop 删除列
```
df.drop(df.columns[0],axis=1,inplace=True) ->删除第一列
df.drop(df.columns[[0,1]],axis=1,inplace=True) ->删除第 0,1 列
df.drop(['id','coef'],axis=1,inplace=True)  删除 'id' 'coef‘ 列
```

- del 删除列
```
del df['two']
```
- pop 删除列
```
three = df.pop('three')
```



## 行操作


### 选择行

```
df[0:3]  -> 切片
df.loc[0:10,['id', 'coef']] -> 选择两列的切片
```

操作 | 语法 | 结果
-- | -- | --
按标签选择行 | df.loc[label] | Series
按整数位置选择行 | df.iloc[loc] | Series
对行切片 | df[5:10] | DataFrame
通过布尔向量选择行 | df[bool_vec] | DataFrame


### 添加新行

```
df.loc[len(df)] = [ 'xxx', 'yyy', 'xxz']
df.loc[len(df), 'name'] = 'xxx'
```

### 删除行

```
df.drop([0,1],inplace=True) 删除 行
```

## 单元格操作

- 位置 + columns
```
df.loc[10,'coef']  -> 10行 ’coef‘ 列
```

- 按位置选择
```
df.iloc[2,1] -> 按位置选择
df.iloc[2] -> 按位置选择
```

- 写指定位置
```
df.at[id[0], 'coef'] = 0  -> 通过标签赋值
df.iat[0, 1] = 0 ->通过位置赋值
df.id[df.name == 'xxx'] = '123'
```

## 条件操作


- 按条件选择
```
df[df.coef> 1]  -> 'coef' 值大于1 的行
df[df.coef.isin([2])] 'coef 是 2的行
df[df.coef.isin([1, 2, 3])] 'coef 是 1, 2, 3的行
```
- 包含字符串的值
```
df.name.str.contains('abc')
df.name.str.contains('abc|abd')
```

- 某个取值范围 (min, max)

```
df[(df.area > min) & (df.area < max)]
```

- 多重条件选择
  - | for or
  - & for and
  - ~ for not
```
df[(df.coef> 1) & (df.coef<3)]  -> 'coef' 值大于1 小于3 的行
```

## Index 操作
- 重置 index
```
dfn = df.reset_index(drop=True) ->重置 index
```
- index 排序
```
df.sort_values(by='B')  -> 按值(列)排序
df.sort_index(axis=1, ascending=False)  -> 按轴排序
```
- 设置 index
```
df.set_index('defect')
```
- 重命名列名
```
df2 = df.rename(columns={'level_0':'date'}) 
```
```
cls_df = cls_df.rename(columns = lambda c:"cls" + str(c))
```

- 读取 CSV 文件时设置 `columns`

```
df = pd.read_csv(csv_path, header=None, names=['xxx','xxx'])
```





## 抽样
### 打乱样本

```
df.sample(n=None, frac=None, replace=False, weights=None, random_state=None, axis=None)
```
> Returns a random sample of items from an axis of object.
frac 为选取的比例 0 ~ 1

```
df = df.sample(frac = 1) 
```
### 按概率抽样

```
s = pd.Series([0,1,2,3,4,5])
example_weights = [0, 0, 0.2, 0.2, 0.2, 0.4]
s.sample(n=3, weights=example_weights)

5    5
4    4
3    3
```

## 其他操作

API | Description
-- | --
`df2.id.str.lower()` |   'id' 列中字符转换小写
`df.T` | 行列转置

### 重复值

```
df.duplicated()  -> 查看重复的
df[df['id'].duplicated()  ->查看 'id' 重复的 keep = False, 'first‘,’last’
df.drop_duplicates(keep='last') -> 删除重复，只留最后一个值
```

### na/NA


```
np.nan -> nan 缺失值
df.dropna(how='any') -> 删除任何带有缺失值的行
df.fillna(value=5) ->填充缺失值
pd.isna(df1) -> 获取值为nan的掩码
```

### 合并 df

```
pe = [df1,df2, df3]
df4 = pd.concat(pe,keys=['0417','0725','0802'], sort=False)
```

### groupby()

