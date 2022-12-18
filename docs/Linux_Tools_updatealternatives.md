---
Title | Linux Tools updatealternatives
-- | --
Created @ | `2020-06-03T06:38:33Z`
Last Modify @| `2022-12-18T06:11:35Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/100)

---
# Reference
- [update-alternatives使用详解](https://www.jianshu.com/p/4d27fa2dce86)

# Brief
-  用于软件多版本切换
  - 显示安装应用的多个版本
  - 安装新的应用版本到管理器
  - 配置应用版本的优先级
  - 移除被管理的版本

## UseCase

- `--display`

```
$ update-alternatives --display python 
python - 手动模式
link best version is /usr/bin/python3.5
链接目前指向 /usr/bin/python2.7
link python is /usr/bin/python
/usr/bin/python2.7 - 优先级 1
/usr/bin/python3.5 - 优先级 2
```

- `--install`

```
# 添加 python link
$ update-alternatives --install /usr/bin/python python /usr/bin/python2.7 2

# 第一个参数: --install 表示向update-alternatives注册服务名。
# 第二个参数: 注册最终地址，成功后将会把命令在这个固定的目的地址做真实命令的软链，以后管理就是管理这个软链；
# 第三个参数: 服务名，以后管理时以它为关联依据。
# 第四个参数: 被管理的命令绝对路径。
# 第五个参数: 优先级，数字越大优先级越高。
```

- `--config`

```
$ update-alternatives --config python    
有 2 个候选项可用于替换 python (提供 /usr/bin/python)。
  选择       路径              优先级  状态
------------------------------------------------------------
  0            /usr/bin/python3.5   2         自动模式
* 1            /usr/bin/python2.7   1         手动模式
  2            /usr/bin/python3.5   2         手动模式

要维持当前值[*]请按<回车键>，或者键入选择的编号：
```

- `--remove`

```
$ update-alternatives –remove python /usr/bin/python2.7
```

## 应用

- Python
- GCC

