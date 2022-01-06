---
Title | cmake commands
-- | --
Create Date | `2022-01-06T08:16:00Z`
Update Date | `2022-01-06T08:18:14Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/249)

---
## Reference
- [cmake commands - manual](https://cmake.org/cmake/help/v3.22/manual/cmake-commands.7.html)
- [string](https://cmake.org/cmake/help/latest/command/string.html)
- [file](https://cmake.org/cmake/help/v3.22/command/file.html)


## Brief
- Scripting Commands
- Project Commands
- Ctest Commands



## Scripting Commands

### string

- 查找/替换/正则匹配
- 拼接/大小写替换/sub-string/...
- 比较/Hash
- ... 详细见 [[cmake string](https://cmake.org/cmake/help/latest/command/string.html)]

### 常用 string 操作

Operations | Pattern | Description
-- | -- | --
FIND |  `string(FIND <string> <substring> <out-var> [...])`
REPLACE | `string(REPLACE <match-string> <replace-string> <out-var> <input>...)`
REGEX MATCH | `string(REGEX MATCH <match-regex> <out-var> <input>...)`
REGEX MATCHALL | `string(REGEX MATCHALL <match-regex> <out-var> <input>...)`
REGEX REPLACE | `string(REGEX REPLACE <match-regex> <replace-expr> <out-var> <input>...)`
TOLOWER | `string(TOLOWER <string> <out-var>)`
TOUPPER | `string(TOUPPER <string> <out-var>)`
LENGTH | `string(LENGTH <string> <out-var>)`
COMPARE | `string(COMPARE <op> <string1> <string2> <out-var>)`


### file

```
Reading
  file(READ <filename> <out-var> [...])
  file(STRINGS <filename> <out-var> [...])
  file(<HASH> <filename> <out-var>)
  file(TIMESTAMP <filename> <out-var> [...])
  file(GET_RUNTIME_DEPENDENCIES [...])

Writing
  file({WRITE | APPEND} <filename> <content>...)
  file({TOUCH | TOUCH_NOCREATE} [<file>...])
  file(GENERATE OUTPUT <output-file> [...])
  file(CONFIGURE OUTPUT <output-file> CONTENT <content> [...])

Filesystem
  file({GLOB | GLOB_RECURSE} <out-var> [...] [<globbing-expr>...])
  file(MAKE_DIRECTORY [<dir>...])
  file({REMOVE | REMOVE_RECURSE } [<files>...])
  file(RENAME <oldname> <newname> [...])
  file(COPY_FILE <oldname> <newname> [...])
  file({COPY | INSTALL} <file>... DESTINATION <dir> [...])
  file(SIZE <filename> <out-var>)
  file(READ_SYMLINK <linkname> <out-var>)
  file(CREATE_LINK <original> <linkname> [...])
  file(CHMOD <files>... <directories>... PERMISSIONS <permissions>... [...])
  file(CHMOD_RECURSE <files>... <directories>... PERMISSIONS <permissions>... [...])

Path Conversion
  file(REAL_PATH <path> <out-var> [BASE_DIRECTORY <dir>] [EXPAND_TILDE])
  file(RELATIVE_PATH <out-var> <directory> <file>)
  file({TO_CMAKE_PATH | TO_NATIVE_PATH} <path> <out-var>)

Transfer
  file(DOWNLOAD <url> [<file>] [...])
  file(UPLOAD <file> <url> [...])

Locking
  file(LOCK <path> [...])

Archiving
  file(ARCHIVE_CREATE OUTPUT <archive> PATHS <paths>... [...])
  file(ARCHIVE_EXTRACT INPUT <archive> [...])
```

## Project Commands


## Ctest Commands
