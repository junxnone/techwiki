---
Title | Markdown Text
-- | --
Create Date | `2021-09-22T10:02:45Z`
Update Date | `2021-09-22T10:15:16Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/160)

---
- **居中对齐**

```
<p align="center ">Here is left</p>
```
<p align="center ">Here is center</p>  

- **左对齐**  
```  
<p align="left">Here is left</p>
```
<p align="left">Here is left</p>

- **右对齐**
```
<p align="right">Here is right</p>
```
<p align="right">Here is right</p>

- superscript & subscript

```
Text Line<sup>superscript</sup>
Text Line<sub>subscript</sub>
```
Text Line<sup>superscript</sup>
Text Line<sub>subscript</sub>

- **转义字符**
```
\* \` \|
```
\* \` \|

- **引用**

```
> 1级引用
>> 2级引用
>>> 3级引用
```
> 1级引用
>> 2级引用
>>> 3级引用

- **Code 引用**

Github issues markdown 引用 code
只能是本repo的code
例如
https://github.com/junxnone/wiki/blob/cbdf0ee17452e221607ae78b5e1ecb5af546cf94/index.04eb6053.js#L5-L7


- **折叠**

````
<details>
<summary>折叠世界</summary>
Hello， 这里是折叠世界

```
Code
Code
```

</details>
````

<details>
<summary>折叠世界</summary>
Hello， 这里是折叠世界

```
Code
Code
```

</details>

- **Keyboard 格式**
```
<kbd>ctrl</kbd> + <kbd>c</kbd>
```
<kbd>ctrl</kbd> + <kbd>c</kbd>


- **Text Color**
 
```
- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `#f03c15` 红
- ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) `#c5f015` 黄 
- ![#1589F0](https://placehold.it/50x15/1589F0/000000?text=+) `#1589F0` 蓝
- ![#1589F0](https://placehold.it/100x50/1589F0/000000?text=1589F0) 
```

- ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) `#f03c15` 红
- ![#c5f015](https://placehold.it/15/c5f015/000000?text=+) `#c5f015` 黄 
- ![#1589F0](https://placehold.it/50x15/1589F0/000000?text=+) `#1589F0` 蓝
- ![#1589F0](https://placehold.it/100x50/1589F0/000000?text=1589F0) 

````
```diff
- text in red
+ text in green
! text in orange
# text in gray
```
````

```diff
- text in red
+ text in green
! text in orange
# text in gray
```
