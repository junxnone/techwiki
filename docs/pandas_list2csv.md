---
Title | pandas list2csv
-- | --
Create Date | `2019-08-12T07:24:10Z`
Update Date | `2022-05-17T12:28:18Z`
Edit link | [here](https://github.com/junxnone/techwiki/issues/278)

---
## Code

```
import pandas as pd
list_a = ["a", "b", "c", "d", "e", "f"]
list_b = [1,2,3,4,5,6]
list_c = ["z", "y", "x", "w", "v", "u"]

pdata = list(zip(list_a, list_b, list_c))
df = pd.DataFrame(data=pdata, columns=['name', 'value', 'new_name'])
df.to_csv('./map_table.csv',index=True,header=True)
```

**df**

name | value | new_name
-- | -- | --
a | 1 | z
b | 2 | y
c | 3 | x
d | 4 | w
e | 5 | v
f | 6 | u

**map_table.csv**
```
,name,value,new_name
0,a,1,z
1,b,2,y
2,c,3,x
3,d,4,w
4,e,5,v
5,f,6,u
```
