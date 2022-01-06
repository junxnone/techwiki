---
Title | cmake commands
-- | --
Create Date | `2022-01-06T08:16:00Z`
Update Date | `2022-01-06T08:16:00Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/249)

---
## Reference
- [cmake commands - manual](https://cmake.org/cmake/help/v3.22/manual/cmake-commands.7.html)

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

## 
