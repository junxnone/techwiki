---
Title | Markdown Table
-- | --
Create Date | `2021-09-22T10:07:37Z`
Update Date | `2021-09-22T10:12:37Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/162)

---
-  **基本格式**

```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3
```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3

> table 中忽略 `|` 使用 `\|`

- **单行 Table**
```
T1 | T2 | T3
-- | -- | --
```
T1 | T2 | T3
-- | -- | --

- **单列 Table**
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

- **Table with task list**
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

- **Table list 添加缩进**
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

- **Table 中换行**
```
T1 | T2<br>T3<br>T4
-- | --
```
T1 | T2<br>T3<br>T4
-- | --

- **html table**

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

