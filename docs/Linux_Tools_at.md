---
Title | Linux Tools at
-- | --
Created @ | `2019-03-10T10:03:14Z`
Last Modify @| `2022-12-20T08:53:25Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/27)

---
## Reference
- [Linux命令之at](https://www.cnblogs.com/diantong/p/9366449.html)

## Brief
- at和batch读取标准输入或一个指定文件，at在指定的时间执行命令

## UseCase

- **Install** 

```
apt-get install at
```

- **at --help**

```
-V 打印版本信息
-q queue 使用指定的队列。队列名称由单个字母组成，有效队列名称范围从a到z和A到Z。
    at默认a队列，batch默认b队列。具有较高字母的队列运行良好。
    特殊队列“=”为正在运行的作业保留。如果作业提交给大写字母指定的队列，
    则该作业被视为在作业时提交给batch。一旦时间到达批处理规则将应用于负载平衡使用中。
    如果atq被赋予指定队列，它将只显示该队列的待处理作业。
-m 即使没有输出也会在作业完成后向用户发出邮件。
-M 不发送邮件给用户
-f file从文件读取而不是标准输出
-l atq的别名
-r atrm的别名
-d atrm的别名
-v 显示在读取作业前作业执行的时间。显示时间格式样例“The Feb 20 14:50:00 1997”
-c 将命令行中列出的作业标记为标准输出
-t time_arg 提交time_arg参数指定作业运行时间，格式[[CC]YY] MMDDhhmm
```
- **Start new task**

```
$ at now +1 min
warning: commands will be executed using /bin/sh
at> echo "hello world">test.txt
at> <EOT>
job 1 at Sun Mar 10 18:27:00 2019

$ at -l
1	Sun Mar 10 18:27:00 2019 a xxx

$ at -c 1
#!/bin/sh
# atrun uid=1000 gid=1000
....
echo "hello world">test.txt
```
> EOT : <kbd>Ctrl</kbd> + <kbd>D</kbd>

```
$ at 5:27
```
```
at -f 2.txt now +1 min
```

- **List the task**

atq列出用户待处理作业（jobs），如果是超级用户，所有用户的（待处理）作业都将被列出。

```
$ atq
2	Sun Mar 10 18:28:00 2019 a xxx
```

## Time format

```
HH：MM 例如：04:00，如果当前以超过设定的时间，则任务在第二天的同一时间执行
HH：MM YYYY-MM-DD 例如04:00 2014-11-11
HH：MM[am|pm] [Month] [Date] 例如 02:00 Dec 12
HH：MM[am|pm] + number [minutes|hours|days|weeks] 例如 now + 10 minutes 
                       表示在某个时间点后多久执行任务
```

