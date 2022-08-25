---
Title | Docker Issues
-- | --
Created @ | `2022-08-25T03:39:44Z`
Last Modify @| `2022-08-25T03:39:44Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/294)

---
## Reference
- [构建Docker镜像时处理'Configuring tzdata'交互输入](https://blog.csdn.net/jiangjiang_jian/article/details/100731400)

## Issues

### Apt Install tzdata 时交互输入

```
 Configuring tzdata
    ------------------
    Please select the geographic area in which you live. Subsequent configuration
    questions will narrow this down by presenting a list of cities, representing
    the time zones in which they are located.
     1. Africa      4. Australia  7. Atlantic  10. Pacific  13. Etc
     2. America     5. Arctic     8. Europe    11. SystemV
     3. Antarctica  6. Asia       9. Indian    12. US
    Geographic area:
```
- **Solution: 禁用交互模式**
```
RUN DEBIAN_FRONTEND=noninteractive apt install -y tzdata
```
