---
Title | Make
-- | --
Create Date | `2021-09-22T02:41:58Z`
Update Date | `2021-09-22T02:41:58Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/80)

---
# Reference
- [How do you get the list of targets in a makefile?](https://stackoverflow.com/questions/4219255/how-do-you-get-the-list-of-targets-in-a-makefile)

# Brief

# UseCase

- list all target

```
list:
    @grep '^[^#[:space:]].*:' Makefile
```
```
make list
```
