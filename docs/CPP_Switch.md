---
Title | CPP Switch
-- | --
Created @ | `2022-05-27T08:22:01Z`
Last Modify @| `2022-05-27T08:23:11Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/289)

---
## Reference
- [将string用于 C++ switch语句](https://ykj373998035.gitbooks.io/c-string-/content/jiang_string_yong_yu_switch_yu_53e528_c_zuo_c_de_s.html)

## Brief 
- C++  中不能使用 `std::string` 作为 case 选项
- 解决方案
  - 使用 `std::map` 置换

## `std::map`

```
#include <map>
#include <string>

enum StringValue { evNotDefined, 
                          evStringValue1, 
                          evStringValue2, 
                          evStringValue3, 
                          evEnd };

std::map<std::string, StringValue> s_mapStringValues;

s_mapStringValues["x"] = evStringValue1;
s_mapStringValues["y"] = evStringValue2;
s_mapStringValues["z"] = evStringValue3;

switch(s_mapStringValues[InputString])
    {
      case evStringValue1:
        cout << "Detected the first valid string." << endl;
        break;
      case evStringValue2:
        cout << "Detected the second valid string." << endl;
        break;
...
...
```

