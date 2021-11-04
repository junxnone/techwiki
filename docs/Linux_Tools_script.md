---
Title | Linux Tools script
-- | --
Create Date | `2021-11-04T08:32:12Z`
Update Date | `2021-11-04T08:42:58Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/205)

---
# Reference
- [【Linux学习 】Linux使用Script命令来记录并回放终端会话](https://blog.csdn.net/ouyang_peng/article/details/78818492)


# Brief
- 记录终端执行命令的历史

```
Usage:
 script [options] [file]

Make a typescript of a terminal session.

Options:
 -a, --append                  append the output
 -c, --command <command>       run command rather than interactive shell
 -e, --return                  return exit code of the child process
 -f, --flush                   run flush after each write
     --force                   use output file even when it is a link
 -o, --output-limit <size>     terminate if output files exceed size
 -q, --quiet                   be quiet
 -t[<file>], --timing[=<file>] output timing data to stderr or to FILE
 -h, --help                    display this help
 -V, --version                 display version
```


## UseCase

Usecase | cmd
-- | --
开始记录 | `script`
保存记录到某个文件 | `script your/log/file`
停止记录 | `exit`
静默方式运行 | `script -q`


- 可以使用 `scriptreplay` 回放的格式
```
$ script -t 2>cmd.time cmd.his
...
run some command
...
$ exit
$ scriptreplay cmd.time cmd.his
```
