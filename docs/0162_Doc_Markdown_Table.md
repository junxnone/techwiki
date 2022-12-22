---
Title | Doc Markdown Table
-- | --
Created @ | `2021-09-22T10:07:37Z`
Last Modify @| `2022-12-22T07:17:59Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/162)

---
## 基本格式

```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3
```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3

> table 中忽略 `|` 使用 `\|`

## 单行 Table

```
T1 | T2 | T3
-- | -- | --
```

T1 | T2 | T3
-- | -- | --


## 单列 Table

```
T1 |
-- |
T2 |
T3 |
````

T1 |
-- |
T2 |
T3 |

## Table with Checklist

```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3
C4 | <ul><li>- [ ] Task 1</li></ul> |<ul><li>- [ ] Task 2</li></ul>
```

T1 | T2 | T3
-- | -- | --
C1 | C2 | C3
C4 | <ul><li>- [ ] Task 1</li></ul> |<ul><li>- [ ] Task 2</li></ul>

## Table list 添加缩进

```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3
C4 |   |<ul><li>[ ] Task 2<ul><li> Task 2.1</li></ul></li></ul>
```

T1 | T2 | T3
-- | -- | --
C1 | C2 | C3
C4 |  |<ul><li>[ ] Task 2<ul><li> Task 2.1</li></ul></li></ul>

## Table 中换行

```
T1 | T2<br>T3<br>T4
-- | --
```

T1 | T2<br>T3<br>T4
-- | --


## html table

<table style="width:100%; table-layout:fixed;">
  <tr>
    <td><img width="150px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_no_strides_transposed.gif"></td>
    <td><img width="150px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/arbitrary_padding_no_strides_transposed.gif"></td>
    <td><img width="150px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/same_padding_no_strides_transposed.gif"></td>
    <td><img width="150px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/full_padding_no_strides_transposed.gif"></td>
  </tr>
  <tr>
    <td>No padding, no strides, transposed</td>
    <td>Arbitrary padding, no strides, transposed</td>
    <td>Half padding, no strides, transposed</td>
    <td>Full padding, no strides, transposed</td>
  </tr>
  <tr>
    <td><img width="150px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif"></td>
    <td><img width="150px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/padding_strides_transposed.gif"></td>
    <td><img width="150px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/padding_strides_odd_transposed.gif"></td>
    <td></td>
  </tr>
  <tr>
    <td>No padding, strides, transposed</td>
    <td>Padding, strides, transposed</td>
    <td>Padding, strides, transposed (odd)</td>
    <td></td>
  </tr>
</table>

### **html table tag `table/tr/td/pre`**

<table style="width:100%; table-layout:fixed;">
  <tr>
  <td>
<pre>
int poly(int *coef, int terms, int x) {
  int power = 1;
  int value = 0;
  for (int j = 0; j < terms; j++) {
    value += coef[j] * power;
    power *= x;
  }
  return value;
}
</pre>
</td>
<td>
<pre>
poly:
  cmp r1, #0
  ble .L4
  push {r4, r5}
  mov r3, r0
  add r1, r0, r1, lsl #2
  movs r4, #1
  movs r0, #0
.L3:
  ldr r5, [r3], #4
  cmp r1, r3
  mla r0, r4, r5, r0
  mul r4, r2, r4
  bne .L3
  pop {r4, r5}
  bx lr
.L4:
  movs r0, #0
  bx lr
</pre>
</td>
</tr>
</table>
