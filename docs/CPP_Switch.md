---
Title | CPP Switch
-- | --
Created @ | `2022-05-27T08:22:01Z`
Last Modify @| `2022-05-27T08:22:01Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/289)

---


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

