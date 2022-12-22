---
Title | Programing Python CodeAnalysis yapf
-- | --
Created @ | `2019-11-14T05:59:05Z`
Last Modify @| `2022-12-22T06:35:40Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/258)

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

