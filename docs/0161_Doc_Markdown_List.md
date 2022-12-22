---
Title | Doc Markdown List
-- | --
Created @ | `2021-09-22T10:05:33Z`
Last Modify @| `2022-12-22T07:17:43Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/161)

---
## 普通 List

```
- list 1
  - list 1.1
    - list 1.1.1
- list 2
- list 3
```

- list 1
  - list 1.1
    - list 1.1.1
- list 2
- list 3


## TODO Task/Check List

```
- [ ] Task 1
  - [ ] Task 1.1
  - [ ] Task 1.2
    - [x] Task 1.2.1
- [ ] Task 2
- [x] Task 3
```

- [ ] Task 1
  - [ ] Task 1.1
  - [ ] Task 1.2
    - [x] Task 1.2.1
- [ ] Task 2
- [x] Task 3


## html 表示 

### 无序 List

```
<ul><li>L1</li><li>L2<ul><li>L2.1<ul><li>L2.1.1</li></ul></li></ul></li><li>L3</li></ul>
```

<ul><li>L1</li><li>L2<ul><li>L2.1<ul><li>L2.1.1</li></ul></li></ul></li><li>L3</li></ul>

### 有序 List

```
<ol><li>L1</li><li>L2<ol><li>L2.1<ol><li>L2.1.1</li></ol></li></ol></li><li>L3</li></ol>
```

<ol><li>L1</li><li>L2<ol><li>L2.1<ol><li>L2.1.1</li></ol></li></ol></li><li>L3</li></ol>


### 自定义 List

```
<ol type="I"><li>第一行</li><li>第二行</li><li>第三行</li></ol>
```

<ol type="I"><li>第一行</li><li>第二行</li><li>第三行</li></ol>



- **type:**
  - a: 小写字母
  - A: 大写字母
  - i: 小写罗马数字
  - I: 大写罗马数字
  - 1: 数字

