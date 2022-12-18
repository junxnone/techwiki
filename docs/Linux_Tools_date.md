---
Title | Linux Tools date
-- | --
Created @ | `2019-08-01T05:38:13Z`
Last Modify @| `2022-12-18T06:09:53Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/8)

---
# Reference

# Brief

- 显示日期时间
```
$ date
Thu Aug  1 13:39:48 UTC 2019
```
- 格式化显示
```
$date  "+%Y-%m-%d  %a  %H:%M:%S"
2019-08-01  Thu  13:40:21
```
```
$date  "+%Y-%m-%d_%H_%M_%S"
2019-08-01_13_41_14
```
-  格式化字符串

String | Description
-- | --
%H |  小时(以00-23来表示)。 
%I  | 小时(以01-12来表示)。 
%K  | 小时(以0-23来表示)。 
%l  | 小时(以0-12来表示)。 
%M  | 分钟(以00-59来表示)。 
%P  | AM或PM。 
%r  | 时间(含时分秒，小时以12小时AM/PM来表示)。 
%s  | 总秒数。起算时间为1970-01-01 00:00:00 UTC。 
%S  | 秒(以本地的惯用法来表示)。 
%T  | 时间(含时分秒，小时以24小时制来表示)。 
%X  | 时间(以本地的惯用法来表示)。 
%Z  | 市区。 
%a  | 星期的缩写。 
%A  | 星期的完整名称。 
%b  | 月份英文名的缩写。 
%B  | 月份的完整英文名称。 
%c  | 日期与时间。只输入date指令也会显示同样的结果。 
%d  | 日期(以01-31来表示)。 
%D |  日期(含年月日)。 
%j  | 该年中的第几天。 
%m  | 月份(以01-12来表示)。 
%U  | 该年中的周数。 
%w  | 该周的天数，0代表周日，1代表周一，异词类推。 
%x |  日期(以本地的惯用法来表示)。 
%y  | 年份(以00-99来表示)。 
%Y  | 年份(以四位数来表示)。 
%n  | 在显示时，插入新的一行。 
%t  | 在显示时，插入tab。 
MM  | 月份(必要) 
DD  | 日期(必要) 
hh  | 小时(必要) 
mm  | 分钟(必要)
ss  | 秒(选择性) 

- 设置时间
```
$ sudo date -s "13:41:00 2019-08-01"
2019年 08月 01日 星期四 13:41:00 CST
```
- 在脚本中插入时间
```
#!/bin/bash
mkdir -p backup_config
cp config.py backup_config/config_$(date "+%Y-%m-%d_%H_%M_%S").py
```
```
$ ls backup_config/
config_2019-08-01_13_47_02.py
```
- 查看多久时间前的日期
```
$ date -d "-1185 day"
2016年 05月 03日 星期二 13:47:51 CST
```
> ±n day/month/year

-  校正时区和时间

```
$ tzselect
Please identify a location so that time zone rules can be set correctly.
Please select a continent, ocean, "coord", or "TZ".
 1) Africa
 2) Americas
 3) Antarctica
 4) Asia
 5) Atlantic Ocean
 6) Australia
 7) Europe
 8) Indian Ocean
 9) Pacific Ocean
10) coord - I want to use geographical coordinates.
11) TZ - I want to specify the time zone using the Posix TZ format.
#? 4
Please select a country whose clocks agree with yours.
 1) Afghanistan           18) Israel                35) Palestine
 2) Armenia               19) Japan                 36) Philippines
 3) Azerbaijan            20) Jordan                37) Qatar
 4) Bahrain               21) Kazakhstan            38) Russia
 5) Bangladesh            22) Korea (North)         39) Saudi Arabia
 6) Bhutan                23) Korea (South)         40) Singapore
 7) Brunei                24) Kuwait                41) Sri Lanka
 8) Cambodia              25) Kyrgyzstan            42) Syria
 9) China                 26) Laos                  43) Taiwan
10) Cyprus                27) Lebanon               44) Tajikistan
11) East Timor            28) Macau                 45) Thailand
12) Georgia               29) Malaysia              46) Turkmenistan
13) Hong Kong             30) Mongolia              47) United Arab Emirates
14) India                 31) Myanmar (Burma)       48) Uzbekistan
15) Indonesia             32) Nepal                 49) Vietnam
16) Iran                  33) Oman                  50) Yemen
17) Iraq                  34) Pakistan
#? 9
Please select one of the following time zone regions.
1) Beijing Time
2) Xinjiang Time
#? 1

The following information has been given:

        China
        Beijing Time

Therefore TZ='Asia/Shanghai' will be used.
Selected time is now:   Tue Nov  5 10:45:12 CST 2019.
Universal Time is now:  Tue Nov  5 02:45:12 UTC 2019.
Is the above information OK?
1) Yes
2) No
#? 1

You can make this change permanent for yourself by appending the line
        TZ='Asia/Shanghai'; export TZ
to the file '.profile' in your home directory; then log out and log in again.

Here is that TZ value again, this time on standard output so that you
can use the /usr/bin/tzselect command in shell scripts:
Asia/Shanghai
```
```
export TZ='Asia/Shanghai' 
```
在 /etc/profile 或 ~/.profile 中 `export TZ` 环境变量
现在时间就是 CST时间了，不再是UTC时间了：
```
Tue Nov  5 10:46:52 CST 2019
```
> UTC - 协调世界时
> UTC  = GMT  格林尼治标准时
> CST = China Standard Time UT+8:00

- 如果时间不对，设置时间

```
sudo date -s 14:00:00
```

- 使用 google http 时间 更新系统时间 - [`ntp` 不同通过 `proxy`]

```
sudo date -s "$(wget -S  "http://www.google.com/" 2>&1 | grep -E '^[[:space:]]*[dD]ate:' | sed 's/^[[:space:]]*[dD]ate:[[:space:]]*//' | head -1l | awk '{print $1, $3, $2,  $5 ,"GMT", $4 }' | sed 's/,//')"
```

# 使用ntp时间

