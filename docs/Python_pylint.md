---
Title | Python pylint
-- | --
Create Date | `2019-11-13T08:10:45Z`
Update Date | `2022-03-28T08:13:33Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/259)

---


## Reference

- [Github - PyCQA](https://github.com/PyCQA/pylint)
- [Docs](http://pylint.pycqa.org/en/latest/user_guide/run.html)
- [如何使用 Pylint 来规范 Python 代码风格](https://www.ibm.com/developerworks/cn/linux/l-cn-pylint/index.html)

## Brief

**Pylint 是一个 Python 代码分析工具，它分析 Python 代码中的错误，查找不符合代码风格标准和有潜在问题的代码。**


**MESSAGE_TYPE 有如下几种：**

- (C) 惯例。违反了编码风格标准
- (R) 重构。写得非常糟糕的代码。
- (W) 警告。某些 Python 特定的问题。
- (E) 错误。很可能是代码中的错误。
- (F) 致命错误。阻止 Pylint 进一步运行的错误。

> 部分问题可以通过 `yapf` / `autopep8` 修复

## Install

```
pip install pylint
```

## UseCase

### 检查单个文件

```
pylint  test.py
```

### 多个文件

```
pylint -ry -j 4 *.py */*.py 
```

### 配置文件

- **生成配置文件**

```
pylint --generate-rcfile > pylint.conf
```

- **使用配置文件**

```
pylint --rcfile=pylint.conf test.py
```

### 配置选项
#### 解决 `c-extension` 导致的问题

-  unsafe-load-any-extension= yes 可以解决掉cv2 的问题
- extension-pkg-whitelist
- `--ignored-modules` 忽略module 可以解决所有问题，但是不推荐

```
pylint  --ignored-modules=openvino.inference_engine,tensorflow,cv2 --errors-only -ry test.py
```


#### 忽略某选项

- `disable`
```
disable=W0108
```
> disable `unnecessary-lambda` option

### 生成报告

```
pylint -ry --rcfile=pylint.conf test.py
```

**Report**

- Statistics by type
- External dependencies
- Raw metrics
- Duplication
- Messages by category
- Messages

<details>
<summary>Report</summary>

```
Report
======
113 statements analysed.

Statistics by type
------------------

+---------+-------+-----------+-----------+------------+---------+
|type     |number |old number |difference |%documented |%badname |
+=========+=======+===========+===========+============+=========+
|module   |1      |NC         |NC         |0.00        |0.00     |
+---------+-------+-----------+-----------+------------+---------+
|class    |0      |NC         |NC         |0           |0        |
+---------+-------+-----------+-----------+------------+---------+
|method   |0      |NC         |NC         |0           |0        |
+---------+-------+-----------+-----------+------------+---------+
|function |1      |NC         |NC         |0.00        |0.00     |
+---------+-------+-----------+-----------+------------+---------+



External dependencies
---------------------
::

    config (train)
    cv2 (train)
    matplotlib (train)
      \-pyplot (train)
    numpy (train)
    pandas (train)
    sklearn
      \-metrics (train)
      \-utils
        \-multiclass (train)
    utils
      \-xxxx (train)
      \-xxxx(train)
      \-xxx(train)
Raw metrics
-----------

+----------+-------+------+---------+-----------+
|type      |number |%     |previous |difference |
+==========+=======+======+=========+===========+
|code      |166    |84.69 |NC       |NC         |
+----------+-------+------+---------+-----------+
|docstring |0      |0.00  |NC       |NC         |
+----------+-------+------+---------+-----------+
|comment   |4      |2.04  |NC       |NC         |
+----------+-------+------+---------+-----------+
|empty     |26     |13.27 |NC       |NC         |
+----------+-------+------+---------+-----------+



Duplication
-----------

+-------------------------+------+---------+-----------+
|                         |now   |previous |difference |
+=========================+======+=========+===========+
|nb duplicated lines      |0     |NC       |NC         |
+-------------------------+------+---------+-----------+
|percent duplicated lines |0.000 |NC       |NC         |
+-------------------------+------+---------+-----------+



Messages by category
--------------------

+-----------+-------+---------+-----------+
|type       |number |previous |difference |
+===========+=======+=========+===========+
|convention |99     |NC       |NC         |
+-----------+-------+---------+-----------+
|refactor   |0      |NC       |NC         |
+-----------+-------+---------+-----------+
|warning    |12     |NC       |NC         |
+-----------+-------+---------+-----------+
|error      |13     |NC       |NC         |
+-----------+-------+---------+-----------+

Messages
--------

+---------------------------+------------+
|message id                 |occurrences |
+===========================+============+
|bad-continuation           |45          |
+---------------------------+------------+
|bad-whitespace             |33          |
+---------------------------+------------+
|import-error               |13          |
+---------------------------+------------+
|unused-import              |11          |
+---------------------------+------------+
|wrong-import-order         |8           |
+---------------------------+------------+
|wrong-import-position      |5           |
+---------------------------+------------+
|line-too-long              |4           |
+---------------------------+------------+
|trailing-whitespace        |2           |
+---------------------------+------------+
|pointless-string-statement |1           |
+---------------------------+------------+
|missing-module-docstring   |1           |
+---------------------------+------------+
|missing-function-docstring |1           |
+---------------------------+------------+




--------------------------------------------------------------------
Your code has been rated at -5.58/10 (previous run: -5.58/10, +0.00)
```
</details>
