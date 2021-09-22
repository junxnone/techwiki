---
Title | Shell exec error check
-- | --
Create Date | `2021-09-22T02:07:35Z`
Update Date | `2021-09-22T02:07:35Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/77)

---
# Brief

- shell中使用符号 `$?` 来显示上一条命令执行的返回值
  - 返回值为 `0` 则代表执行成功
  - 其他表示失败

```
if [ $? -ne 0 ]; then
    echo "failed"
    exit 0
else
    echo "succeed"
fi
```
