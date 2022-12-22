---
Title | Programing Python assert
-- | --
Created @ | `2019-11-15T06:21:57Z`
Last Modify @| `2022-12-22T06:36:29Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/262)

---
## Reference

- [bandit - B101: Test for use of assert](https://bandit.readthedocs.io/en/latest/plugins/b101_assert_used.html)
- [The assert statement](https://docs.python.org/3/reference/simple_stmts.html#the-assert-statement)
- [python断言(assert) 与 __debug__](https://blog.csdn.net/You_are_my_dream/article/details/53328293)

## Brief

**Python assert（断言）用于判断一个表达式，在表达式条件为 false 的时候触发异常。**
```
assert expression [, arguments]
```
![image](https://user-images.githubusercontent.com/2216970/68921341-6a2b8980-07b3-11ea-8a9f-5644930cffea.png)

`assert expression` == 
```
if __debug__:
    if not expression: raise AssertionError
```

- 当使用参数 `-o` 时会被优化掉，产生风险
> `-o` 时 设置 `__debug__` 为 `False`, 正常状态为 `True`

## UseCase

```
In [1]: assert True

In [2]: assert False
---------------------------------------------------------------------------
AssertionError                            Traceback (most recent call last)
<ipython-input-2-a871fdc9ebee> in <module>
----> 1 assert False

AssertionError:

In [3]: assert False,' is error'
---------------------------------------------------------------------------
AssertionError                            Traceback (most recent call last)
<ipython-input-3-332431e19970> in <module>
----> 1 assert False,' is error'

AssertionError:  is error

```

##  bandit 报错

```
>> Issue: [B101:assert_used] Use of assert detected. The enclosed code will be removed when compiling to optimised byte code.
   Severity: Low   Confidence: High
   Location: plot_gtdt.py:367
   More Info: https://bandit.readthedocs.io/en/latest/plugins/b101_assert_used.html
366
367         assert len(net.inputs.keys(
368         )) == 1, "Sample supports only YOLO V3 based single input topologies"

```

- 修改方式

```
if len(net.inputs.keys()) != 1:
    print("Sample supports only YOLO V3 based single input topologies")
    sys.exit(1)
```
