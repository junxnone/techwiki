---
Title | pandas sort
-- | --
Create Date | `2019-08-15T01:58:49Z`
Update Date | `2022-05-17T12:29:38Z`
Edit link | [here](https://github.com/junxnone/techwiki/issues/279)

---
- sort_value
- sort_index

## 参数

```
axis：0按照行名排序；1按照列名排序
ascending：默认True升序排列；False降序排列
inplace：默认False，否则排序之后的数据直接替换原来的数据框
kind：排序方法，{‘quicksort’, ‘mergesort’, ‘heapsort’}, default ‘quicksort’
na_position：缺失值默认排在最后{"first","last"}
by：按照某一列(行)或几列(行)数据进行排序
```

> 指定多列（多行）排序时，先按排在前面的列（行）排序，如果内部有相同数据，再对相同数据内部用下一个列（行）排序

## sort_index
- 按“行标签”升序排列
- 按“列标签”升序排列
- 指定“多列”排序

## sort_value
- 按b列升序排序
- 先按b列降序，再按a列升序排序
- 按行3升序排列
- 按行3升序，行0降排列
