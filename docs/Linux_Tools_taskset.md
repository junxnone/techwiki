---
Title | Linux Tools taskset
-- | --
Created @ | `2020-03-20T02:55:19Z`
Last Modify @| `2022-12-18T06:10:42Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/102)

---
# Brief
-  指定运行 cpu

```
taskset -c 0,1 your_app
```

-  `--help`

```
Options:
 -a, --all-tasks         operate on all the tasks (threads) for a given pid
 -p, --pid               operate on existing given pid
 -c, --cpu-list          display and specify cpus in list format
 -h, --help              display this help
 -V, --version           display version

The default behavior is to run a new command:
    taskset 03 sshd -b 1024
You can retrieve the mask of an existing task:
    taskset -p 700
Or set it:
    taskset -p 03 700
List format uses a comma-separated list instead of a mask:
    taskset -pc 0,3,7-11 700
Ranges in list format can take a stride argument:
    e.g. 0-31:2 is equivalent to mask 0x55555555
```
