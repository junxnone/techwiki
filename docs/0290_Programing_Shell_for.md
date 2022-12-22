---
Title | Programing Shell for
-- | --
Created @ | `2022-06-16T02:45:07Z`
Last Modify @| `2022-12-22T06:41:32Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/290)

---
## Reference
- [Shell中for循环的几个常用写法](https://blog.csdn.net/babyfish13/article/details/52981110)

## Brief
- 数字循环
- 字符循环
- 路径查找


## 数字循环

### i++

```
for((i=1;i<=10;i++));
do 
echo $(expr $i \* 3 + 1);
done
```

### `..` 生成值

```
for i in {1..10}
do
echo $(expr $i \* 3 + 1);
done
```

### seq 生成值

```
for i in $(seq 1 10)
do 
echo $(expr $i \* 3 + 1);
done
```

## 字符循环

### 遍历字符串

```
for i in `ls`;
do 
echo $i is file name\! ;
done
```

### 输入参数遍历

```
for i in $* ;
do
echo $i is input chart\! ;
done
```

## 遍历多个变量

```
for i in f1 f2 f3 ;
do
echo $i is appoint ;
done
```

### 遍历变量中的字符串

```
list="rootfs usr data data2"
for i in $list;
do
echo $i is appoint ;
done
```

## 路径查找

### 遍历路径

```
for file in /proc/*;
do
echo $file is file path \! ;
done
```

### 遍历 `ls` 结果

```
for file in $(ls *.sh)
do
echo $file is file path \! ;
done
```
