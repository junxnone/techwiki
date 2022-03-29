---
Title | Python list
-- | --
Create Date | `2019-05-29T17:10:44Z`
Update Date | `2022-03-29T09:35:19Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/267)

---
## Brief

Name | Description
-- | --
复制 | `list1 = list2`
深度 复制 | `list1 = list2[:]`
合并 | `list1 = list2 + list3`<br> `list1 += list2` <br> `list1.extend(list2)`
切片 | `list1[0:0] = list2`<br>`list1[1:1]=list2`<br>`list1[::2]`<br>`list1[1::2]`
list2str | `str = ''.join(list1)`

## Examples
### 复制
L1 = L      #L1为L的别名，用C来说就是指针地址相同，对L1操作即对L操作。函数参数就是这样传递的
L1 = L[:]   #L1为L的克隆，即另一个拷贝。

### 合并

- `a + b`

```
>>> a = ['a','b','c','d']
>>> b = [1,2,3,4]
>>> c = a + b
>>> c
['a', 'b', 'c', 'd', 1, 2, 3, 4]
```

- `a += b`

```
>>> a += b
>>> a
['a', 'b', 'c', 'd', 1, 2, 3, 4]
```

- `a.extend(b)`

```
>>> a.extend(b)
>>> a
['a', 'b', 'c', 'd', 1, 2, 3, 4]
```

### 切片

```
>>> a[0:0] = b
>>> a
[1, 2, 3, 4, 'a', 'b', 'c', 'd']
```

```
>>> a[1:1] = b
>>> a
['a', 1, 2, 3, 4, 'b', 'c', 'd']
```

- 奇偶切片

```
In [6]: a
Out[6]: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

In [7]: a[::2]
Out[7]: [0, 2, 4, 6, 8]

In [8]: a[1::2]
Out[8]: [1, 3, 5, 7, 9]
```


### 判断是否为空

```
if a:
# 非空
else:
# 空
```
```
if len(a):
# 非空
else:
# 空
```

>Python if 条件 False,0,'',[],{},()都可以视为假。

### list2string

```
str = ''.join(list)
```

