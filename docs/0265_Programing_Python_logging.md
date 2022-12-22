---
Title | Programing Python logging
-- | --
Created @ | `2020-05-26T07:52:14Z`
Last Modify @| `2022-12-22T06:39:29Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/265)

---


## Reference
- [Python之路(第十七篇)logging模块](https://www.cnblogs.com/Nicholas0707/p/9021672.html)

## Brief
- 自带 log 打印管理工具


### Log Level 定义

Level | Description
-- | --
**DEBUG** | 详细信息，典型地调试问题时会感兴趣。 详细的debug信息。
**INFO** | 证明事情按预期工作。 关键事件。
**WARNING** | 表明发生了一些意外，或者不久的将来会发生问题（如‘磁盘满了’）。软件还是在正常工作。
**NOTICE** | 不是错误，但是可能需要处理。普通但是重要的事件。
**ERROR** | 由于更严重的问题，软件已不能执行一些功能了。 一般错误消息。
**CRITICAL** | 严重错误，表明软件已不能继续运行了。
**ALERT** | 需要立即修复，例如系统数据库损坏。
**EMERGENCY** | 紧急情况，系统不可用（例如系统崩溃），一般会通知所有用户。


## UseCase

函数 | 说明
-- | --
logging.debug(msg, *args, **kwargs) | 创建一条严重级别为DEBUG的日志记录
logging.info(msg, *args, **kwargs) | 创建一条严重级别为INFO的日志记录
logging.warning(msg, *args, **kwargs) | 创建一条严重级别为WARNING的日志记录
logging.error(msg, *args, **kwargs) | 创建一条严重级别为ERROR的日志记录
logging.critical(msg, *args, **kwargs) | 创建一条严重级别为CRITICAL的日志记录
logging.log(level, *args, **kwargs) | 创建一条严重级别为level的日志记录
logging.basicConfig(**kwargs) | 对root logger进行一次性配置


## Examples

```
import logging
def get_logger(name=__name__):
    logger = logging.getLogger(name)
    logger.setLevel(logging.DEBUG)
    formatter = logging.Formatter('%(levelname)s %(asctime)s %(filename)s L%(lineno)s: %(message)s')
    consoleHandler = logging.StreamHandler()
    consoleHandler.setFormatter(formatter)
    consoleHandler.setLevel(logging.DEBUG)
    logger.addHandler(consoleHandler)
    return logger

log = get_logger()
log.info('test logging')
```
```
INFO 2020-09-09 02:51:06,311 test.py L15: test logging
```
