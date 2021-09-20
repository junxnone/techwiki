---
Title | tmux arch
-- | --
Create Date | `2021-09-20T04:36:10Z`
Update Date | `2021-09-20T04:36:10Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/30)

---
# Reference
- [为什么使用tmux](https://www.cnblogs.com/itech/archive/2012/12/17/2822170.html)
- [tmux wiki](https://github.com/tmux/tmux/wiki)
 
# Brief

- C/S架构 确保任务可以继续执行

## 层属关系

- Sessions - 可以包含多个 `Windows`
  - Windows - 可以包含多个 `Panes`
    - Panes

```
(0)  - session_1: 2 windows
(1)  ├─> + 0: bash- (3 panes)
(2)  └─> + 1: bash* (2 panes)
(3)  - session_2: 1 windows
(4)  └─> + 0: bash* (2 panes)
(5)  - session_3: 1 windows (attached)
(6)  └─> + 0: bash* (2 panes)
```

![image](https://user-images.githubusercontent.com/2216970/83627181-1f475700-a5c9-11ea-90d1-45eaeb21f235.png)



- 可以使用如下对应关系工作:
  - `Session`  - `Project`
  - `Windows` - `Task`
  - `Pane` - `Details`


