---
Title | Linux Tools rename
-- | --
Created @ | `2018-12-14T07:28:47Z`
Last Modify @| `2022-12-20T09:01:07Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/91)

---
## UseCase


Usecase | cmd
-- | --
添加前缀 `frame` | `rename 's/^/frame_/' *`
替换当前目录下所有文件名中的 `xxx` 为 `sss` | `rename 's/xxx/sss/' *`

> 特殊字符需添加转义符号 `\`
> -n  no action ，只看看会改成什么样


## Examples

- **rename frame_xxx.png to frame_0xxx.png**

```

├── frame_000.png
├── frame_100.png
├── frame_200.png
├── frame_300.png
├── frame_400.png
├── frame_500.png
├── frame_600.png
└── frame_700.png
```

```
rename 's/frame_/frame_0/' *
```
```
.
├── frame_0000.png
├── frame_0100.png
├── frame_0200.png
├── frame_0300.png
├── frame_0400.png
├── frame_0500.png
├── frame_0600.png
└── frame_0700.png
```

