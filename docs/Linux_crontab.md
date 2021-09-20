---
Title | Linux crontab
-- | --
Create Date | `2021-09-20T03:52:38Z`
Update Date | `2021-09-20T03:52:38Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/25)

---

# Brief

# Usecase

- **Add new task**

```
# crontab -e
```
```
# m h  dom mon dow   command
0 0 * * 1  /home/xxxx/restart_ssserver.sh
```

> 每周一零时执行脚本 restart_ssserver.sh

## Time Format

```
{minute} {hour} {day-of-month} {month} {day-of-week} {full-path-to-shell-script} 
o minute: 区间为 0 – 59 
o hour: 区间为0 – 23 
o day-of-month: 区间为0 – 31 
o month: 区间为1 – 12. 1 是1月. 12是12月. 
o Day-of-week: 区间为0 – 7. 周日可以是0或7.
```

