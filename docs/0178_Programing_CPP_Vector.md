---
Title | Programing CPP Vector
-- | --
Created @ | `2021-08-05T06:17:24Z`
Last Modify @| `2022-12-22T06:26:12Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/178)

---
# Reference
- [C++ vector swap()去除多余容量（详解版）](http://c.biancheng.net/view/7403.html)

# Brief

- **方法**
  - push_back()
  - insert()
  - emplace()
  - swap()
  - reserve()

# UseCase

## insert()

用法 | 用例
-- | --
在 pos 处插入 elem | `insert(pos,elem)`
在 pos 处插入 n 个 elem | `insert(pos,n,elem)`
在 pos 处插入其他容器 [first, end] 区域元素 | `insert(pos,first,last)`
在 pos 处插入初始化列表 {a, b, c, ...}| `insert(pos,initlist)`

## swap()

用法 | 用例
-- | --
交换 2 个相同类型的 vector 容器<br>交换容量和存储的所有元素 | `vector_a.swap(vector_b);`
去除当前 vector 容器多余的容量 | `vector<T>(x).swap(x);`
清空vector容器 | `vector<T>().swap(x);`

