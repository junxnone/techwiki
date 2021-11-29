---
Title | YAML
-- | --
Create Date | `2021-11-29T06:16:46Z`
Update Date | `2021-11-29T06:16:46Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/229)

---
## Reference
- [YAML Spec](https://yaml.org/spec/)
- **pyyaml** [[code](https://github.com/yaml/pyyaml)] [[docs](https://pyyaml.org/wiki/PyYAMLDocumentation)]
  - [python：yaml模块](https://www.jianshu.com/p/eaa1bf01b3a6)
- **ruamel.yaml** [[code](https://sourceforge.net/p/ruamel-yaml/code/ci/default/tree/)] [[docs](https://yaml.readthedocs.io/en/latest/)]
  - [ruamel.yaml - Differences with PyYAML](https://yaml.readthedocs.io/en/latest/pyyaml.html)

## Brief
- YAML - `Yet Another Markup Language` - 类似 `xml/json`
- **用途**
  - yaml 作为配置文件 （kubernetes/docker/...)
- **python parser package**
  - pyyaml - `官方 package`
  - ruamel.yaml
- **File**  - `your_file.yml`


## YAML 语言规则

- 使用缩进表示层级关系
  - 使用空格键缩进
  - 缩进的空格数，相同层级对齐即可
- 注释标识为 `#`
- 大小写敏感
- 支持数据类型 - `对象/数组/纯量`
- **对象**
  -  `key: value` - `:` 后面加空格
- **数组**
  - 以 `-` 开头的行表示构成一个数组
  - 多维数组表示 - `key: [value1, value2, ...]`
- **纯量** `-` 后面直接跟 `int/float/string/boolen/...`

---

- yaml键值对：即python中字典
- yaml键值对嵌套：即python中字典嵌套字典
- yaml数组
- yaml键值对中嵌套数组
-  yaml"数组"中嵌套"键值对"
- yaml文件中基本数据类型

### `yaml.load` vs `yaml.safe_load`

```
Warning: It is not safe to call yaml.load with any data received from an untrusted source!
yaml.load is as powerful as pickle.load and so may call any Python function. 
Check the yaml.safe_load function though.
```



## History

- 2004.01.29 `spec 1.0`
- 2004.12.30 `spec 1.1`
- 2010.20.01 `spec 1.2`
