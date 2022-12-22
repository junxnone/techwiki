---
Title | Tools VisualStudio
-- | --
Created @ | `2021-11-19T03:43:20Z`
Last Modify @| `2022-12-22T07:22:09Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/222)

---
## Reference
- [`/permissive-`(标准符合性)](https://docs.microsoft.com/zh-cn/cpp/build/reference/permissive-standards-conformance?view=msvc-170)

## Tips
- VS2019 中不含 C++11 标准，编译 nanoflann(C++11) 时 需要 `Conformance mode` 选 no, 即 `/permissive`

### 查看 CV:Mat 数据

```
img = cv::Mat::zeros(rows, cols, CV_32FC1);

```
- 在 Watch 窗口查看 img[0:15] 的数据
```
(float*)(img.data),16
```
