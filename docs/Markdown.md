---
Title | Markdown
-- | --
Create Date | `2018-11-22T09:13:38Z`
Update Date | `2021-09-22T10:00:05Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/158)

---
# Reference
- [html2markdown](http://www.bejson.com/convert/html2markdown/)
- [mdv：基于终端的 Markdown 查看器](https://linuxtoy.org/archives/mdv.html)
- [emoji sheet](https://www.webfx.com/tools/emoji-cheat-sheet/)
- [MarkDown 合并表格 - html](https://www.jianshu.com/p/f098d508571f)
  - [excel2html - No-Cruft Excel to HTML Table Converter](http://pressbin.com/tools/excel_to_html_table/index.html)

# 文字
- 居中对齐

```
<p align="center ">Here is left</p>
```
<p align="center ">Here is center</p>  

- 左对齐  
```  
<p align="left">Here is left</p>
```
<p align="left">Here is left</p>

- 右对齐
```
<p align="right">Here is right</p>
```
<p align="right">Here is right</p>

- superscript & subscript

```
Text Line<sup>superscript</sup>
Text Line<sub>subscript</sub>
```
Text Line<sup>superscript</sup>
Text Line<sub>subscript</sub>

- 转义字符
```
\* \` \|
```
\* \` \|


# Task List

- [ ] Task 1
  - [ ] Task 2
- [x] Task 3

- html 表示 无序
```
<ul><li>第一行</li><li>第二行</li><li>第三行</li></ul>
```
<ul><li>第一行</li><li>第二行</li><li>第三行</li></ul>

- html 表示 有序
```
<ol><li>第一行</li><li>第二行</li><li>第三行</li></ol>
```

<ol><li>第一行</li><li>第二行</li><li>第三行</li></ol>

```
<ol type="I"><li>第一行</li><li>第二行</li><li>第三行</li></ol>
```
<ol type="I"><li>第一行</li><li>第二行</li><li>第三行</li></ol>

**type:**
- a: 小写字母
- A: 大写字母
- i: 小写罗马数字
- I: 大写罗马数字
- 1: 数字

# Table 
-  Basic Table

```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3
```
T1 | T2 | T3
-- | -- | --
C1 | C2 | C3

> table 中忽略 ‘|’ 使用 ‘\\\|’

- 单行 Table
```
T1 | T2 | T3
-- | -- | --
```
T1 | T2 | T3
-- | -- | --

- 单列 Table
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

- Table with task list
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

- Table list 添加缩进
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

- Table 中换行
```
T1 | T2<br>T3<br>T4
-- | --
```
T1 | T2<br>T3<br>T4
-- | --

- html table

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

# 引用
```
> 1级引用
>> 2级引用
>>> 3级引用
```
> 1级引用
>> 2级引用
>>> 3级引用

# html 标签

- 折叠

````
<details>
<summary>折叠世界</summary>
Hello， 这里是折叠世界

```
Code
Code
```

</details>
````

<details>
<summary>折叠世界</summary>
Hello， 这里是折叠世界

```
Code
Code
```

</details>

- Keyboard
```
<kbd>ctrl</kbd> + <kbd>c</kbd>
```
<kbd>ctrl</kbd> + <kbd>c</kbd>

# Color 
```
- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `#f03c15` 红
- ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) `#c5f015` 黄 
- ![#1589F0](https://placehold.it/50x15/1589F0/000000?text=+) `#1589F0` 蓝
- ![#1589F0](https://placehold.it/100x50/1589F0/000000?text=1589F0) 
```

- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `#f03c15` 红
- ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) `#c5f015` 黄 
- ![#1589F0](https://placehold.it/50x15/1589F0/000000?text=+) `#1589F0` 蓝
- ![#1589F0](https://placehold.it/100x50/1589F0/000000?text=1589F0) 

````
```diff
- text in red
+ text in green
! text in orange
# text in gray
```
````

```diff
- text in red
+ text in green
! text in orange
# text in gray
```

# Image
- 图片缩放
- 也可以直接使用 size ` width="500" height="500"`
```
<img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="50%" height="50%">
```
50% | <img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="50%" height="50%">
-- | --
10% | <img src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif" alt="alt text" width="10%" height="10%">
300px | <img width="300px" src="https://raw.githubusercontent.com/junxnone/conv_arithmetic/master/gif/no_padding_strides_transposed.gif">

# Code 引用

Github issues markdown 引用 code
只能是本repo的code
例如
https://github.com/junxnone/wiki/blob/cbdf0ee17452e221607ae78b5e1ecb5af546cf94/index.04eb6053.js#L5-L7
