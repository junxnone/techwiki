---
Title | Shell for
-- | --
Created @ | `2022-06-16T02:45:07Z`
Last Modify @| `2022-06-16T02:45:07Z`
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

### `..`

```
for i in {1..10}
do
echo $(expr $i \* 3 + 1);
done
```

### seq

```
for i in $(seq 1 10)
do 
echo $(expr $i \* 3 + 1);
done
```


