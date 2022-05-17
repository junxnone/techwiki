---
Title | pandas SettingWithCopyWarning
-- | --
Create Date | `2019-08-14T10:33:31Z`
Update Date | `2022-05-17T14:05:18Z`
Edit link | [here](https://github.com/junxnone/techwiki/issues/281)

---
## Reference
- [Pandas 中 SettingwithCopyWarning 的原理和解决方案](https://www.jianshu.com/p/72274ccb647a)

## Error Log
```
SettingWithCopyWarning: A value is trying to be set on a copy of a slice from a DataFrame
```
- 操作可能没有按预期运行，需要检查结果以确保没有出错。


## Solution
- 如果要更改原始数据，使用单一赋值操作（loc）
- 如果想要一个副本，确保强制让 Pandas 创建副本 `.copy()`
- 关闭警告的设置方法: `pd.set_option('mode.chained_assignment', None)`

## Details
Pandas 中的某些操作会返回数据的视图（View），某些操作会返回数据的副本（Copy）

