---
Title | cmake debug
-- | --
Create Date | `2022-01-02T04:17:20Z`
Update Date | `2022-01-02T04:17:20Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/241)

---
## Reference
- [message](https://cmake.org/cmake/help/latest/command/message.html)

## message 打印信息
- 普通 log
```
message([<mode>] "message text" ...)  
```

- 检查状态
```
message(<checkState> "message text" ...)
```

### mode


mode | Description
-- | --
FATAL_ERROR | 停止执行, 停止生成
SEND_ERROR | 继续执行, 停止生成
WARING | 继续执行
AUTHOR_WARNING | Dev mode 继续执行
DEPRECATION | 弃用 的 错误或警告
NOTICE | 让用户注意的信息
STATUS | 打印状态信息
VERBOSE |  详细信息
DEBUG | debug 信息
TRACE |


```
message(STATUS "Your Message")
```

### CheckState

checkstate | Description
-- | --
CHECK_START | 检查之前的信息
CHECK_PASS | 检查成功
CHECK_FAIL | 检查失败


