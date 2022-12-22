---
Title | Build Cmake InstallFiles
-- | --
Created @ | `2022-01-05T03:17:53Z`
Last Modify @| `2022-12-22T06:04:00Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/247)

---
## Reference
- [Installing Files - Mastering CMake](https://cmake.org/cmake/help/book/mastering-cmake/chapter/Install.html)
- [install command](https://cmake.org/cmake/help/latest/command/install.html#command:install)

## Brief

```
install(TARGETS <target>... [...])
install(IMPORTED_RUNTIME_ARTIFACTS <target>... [...])
install({FILES | PROGRAMS} <file>... [...])
install(DIRECTORY <dir>... [...])
install(SCRIPT <file> [...])
install(CODE <code> [...])
install(EXPORT <export-name> [...])
install(RUNTIME_DEPENDENCY_SET <set-name> [...])
```


