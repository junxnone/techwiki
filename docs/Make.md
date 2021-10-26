---
Title | Make
-- | --
Create Date | `2020-06-05T06:50:28Z`
Update Date | `2021-10-26T04:23:05Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/80)

---
# Reference
- [How do you get the list of targets in a makefile?](https://stackoverflow.com/questions/4219255/how-do-you-get-the-list-of-targets-in-a-makefile)

# Brief
- make tools
  - **GNU Make**
  - QT qmake
  - MS nmake
  - BSD pmake





# UseCase

- list all target

```
list:
    @grep '^[^#[:space:]].*:' Makefile
```
```
make list
```
