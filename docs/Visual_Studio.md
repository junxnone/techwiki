---
Title | Visual Studio
-- | --
Create Date | `2021-11-19T03:43:20Z`
Update Date | `2022-04-11T09:32:08Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/222)

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
