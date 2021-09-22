---
Title | Ubuntu json tools
-- | --
Create Date | `2021-09-22T07:27:40Z`
Update Date | `2021-09-22T07:27:40Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/125)

---
# Reference
- [fx github repo](https://github.com/antonmedv/fx)
- [jq处理JSON数据, jq Manual (development version)](https://www.cnblogs.com/timxgb/p/6644914.html)
- [Linux中在命令行中使用JQ来解析修改JSON字符串](https://www.jianshu.com/p/f50c87b7eaea)
- [jq Manual](https://stedolan.github.io/jq/manual/)
- [jq Github repo - Command-line JSON processor](https://github.com/stedolan/jq)

# Brief
- json tools
  - jq
  - fx
 
## jq

```
sudo apt install jq
```
```
jq . xxx.json
```

- 查询部分属性

```
cat xxx.json |jq '.categories'
cat xxx.json |jq '.info.year'
```

## fx

```
sudo -E npm install -g fx
```
```
fx xxx.json
```

## 使用 `Vi` 修改 `json`
```
vi xxxx.json
:%!jq .
```

