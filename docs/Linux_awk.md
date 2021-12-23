---
Title | Linux awk
-- | --
Create Date | `2018-11-29T10:51:42Z`
Update Date | `2021-12-23T15:33:13Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/44)

---
## Reference
- [AWK用法入门详解](https://www.cnblogs.com/losbyday/p/5854707.html)
- [The GNU Awk User’s Guide](http://www.gnu.org/software/gawk/manual/gawk.html)
- [awk匹配案例](https://blog.csdn.net/qq_42224274/article/details/82584801)
- [awk用法之：文本替换](https://www.jianshu.com/p/d90f8a2ecd62)

## Brief

**awk是一个强大的文本分析工具**

相对于grep的查找，sed的编辑，awk在其对数据分析并生成报告时，显得尤为强大。简单来说awk就是把文件逐行的读入，以空格为默认分隔符将每行切片，切开的部分再进行各种分析处理。
awk有3个不同版本: awk、nawk和gawk，未作特别说明，一般指gawk，gawk 是 AWK 的 GNU 版本。

## UseCase
```
awk '{pattern + action}' {filenames}
```

Usecase | cmd
-- | --
打印出每一行中的第n个选项(默认空格分割) | `awk '{print $n}' xxx`
指定分隔符 | `grep "bash" /etc/passwd \| awk -F ':' '{print $1,$7}'`
指定分隔符单引号  `'` | `grep "bash" /etc/passwd \| awk -F '\047' '{print $1,$7}'` <br> - `\047` 十进制 `'` <br> - `\x27` 十六进制 `'`
$NF  指定倒数第1列 | `grep "bash" /etc/passwd \| awk -F ':' '{print $NF}'`
$(NF-1)  指定倒数第2列 | `grep "bash" /etc/passwd \| awk -F ':' '{print $(NF-1)}'`
多字符匹配 | 匹配包含root或net或ucp的任意行 `awk '/(root|net|ucp)/' /etc/passwd`
print 中间添加其他字符 | `cat inf_log.txt \|awk -F ' ' '{print $1,"\|",$5,"\|",$7}'`
查询某字符串 `string` 在文件中出现的次数 | `awk -v RS="@#$j" '{print gsub(/string/,"&")}' yourfile`
`shell` 查询某变量在 文件中出现的次数 | `awk -v RS="@#$j" '{print gsub(/'$text_id'/,"&")}'  yourfile`
计算数值时打印浮点数 | `awk 'BEGIN{printf "%.3f\n", '$tcnt'/'$totalcnt'}'`
查询 $5 等于 string 的行 | `awk '$5==string {print $0}' yourfile`
查询 $5 等于 string $6 等于 string2 的行 | `awk '$5==string && $6==string2 {print $0}' yourfile`
获取外部变量 | `awk -F '[/_ ]' '$2!=teid {print $6}' teid="$text_id"`<br> - `-F '[/_ ]'`  使用多个分隔符 `/` `_` 和 ` ` <br>- `awk -F '[\| ]+'`  使用 `+` 将连续出现的分隔符当做一个来处理

## 替换字符
> awk的sub/gsub函数用来替换字符串

Usecase | cmd
-- | --
替换每行的第一个 `AAAA` | `awk '{ sub(/AAAA/,"BBBB"); print $0 }' t.txt`
替换所有的 `AAAA` | `awk '{ gsub(/AAAA/,"BBBB"); print $0 }' t.txt`
替换满足条件的行的 `AAAA` | `awk '/CCCC/ { gsub(/AAAA/,"BBBB"); print $0; next } { print $0 }' t.txt`<br>- 替换出现 `CCCC` 的行中的 `AAAA`
替换多个可选串 `AAAA` & `CCCC` | `awk '{ gsub(/AAAA|aaaa/,"BBBB"); print $0 }' t.txt`
全字匹配替换 | `awk '{ sub(/\<AAAA\>/,"BBBB"); print $0 }' t.txt`
规则表达式匹配 | `awk '{ gsub(/^A*/,"B"); print $0 }' t.txt`<br>- 以A开头的字符串

## 使用bash 执行拼接的命令

- **重命名文件**
```
ls */*|awk -F '/' '{print "mv "$1"/"$2" "$1"_"$2}'|bash
```

> 将文件夹 `$1` 下的 `$2` 移到当前目录，并重命名为 `$1_$2` 的格式

## 打印除特定位置外的字符串

**打印使用 `/` 分割后除第一个和最后一个之外的字符串**
```
awk -F '/' '{for(i=2;i<NF;++i) printf $i"/";printf "\n"}'
```
