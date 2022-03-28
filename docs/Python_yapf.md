---
Title | Python yapf
-- | --
Create Date | `2019-11-14T05:59:05Z`
Update Date | `2022-03-28T08:10:35Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/258)

---

## Reference
- [Github - Google](https://github.com/google/yapf)

## Brief
- **Google 开发的一款python code 格式化工具**


## UseCase

- 查看会更改哪些内容

```
yapf -d your_code.py
```

- 直接替换源文件

```
yapf -i your_code.py
```

- style: 可选 `pep8` 或 `google` , 默认是 `pep8`

```
yapf -i --style google your_code.py
```

