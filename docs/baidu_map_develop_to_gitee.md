---
Title | baidu map develop to gitee
-- | --
Create Date | `2021-02-13T03:29:16Z`
Update Date | `2022-04-10T14:29:29Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/153)

---
## Q?
### 引用资源 
- 部署到 gitee 的路径问题，要使用 `/repo_name/path/` 路径 来访问资源

### json 加载
- json加载问题，不清楚为什么不能加载 `*.geojson` 文件
  -  **workaround :** [html 引入 json文件](https://jingyan.baidu.com/article/335530dafd173619cb41c30c.html)

- 包含文件
```
<script type="text/javascript" src=["/goto/data/go.geojson"]()></script>
```
- 声明变量
```
var geojson_go = {
  "type": "FeatureCollection",
...
...
}
```
- 使用
```
var darray = geojson_go.features

```
