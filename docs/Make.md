---
Title | Make
-- | --
Create Date | `2020-06-05T06:50:28Z`
Update Date | `2022-01-02T03:59:27Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/80)

---
# Reference
- [How do you get the list of targets in a makefile?](https://stackoverflow.com/questions/4219255/how-do-you-get-the-list-of-targets-in-a-makefile)

# Brief
- **make tools**: 不同的工具 `Makefile` 格式也不同
  - **GNU Make**
  - QT qmake
  - MS nmake
  - BSD pmake
- [[cmake]] 可以做到 `Write Once, Run Everywhere`





# UseCase

- list all target

```
list:
    @grep '^[^#[:space:]].*:' Makefile
```
```
make list
```
