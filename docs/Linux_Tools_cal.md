---
Title | Linux Tools cal
-- | --
Create Date | `2021-10-23T11:01:19Z`
Update Date | `2021-10-23T11:01:19Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/188)

---

# Brief
- cal - 显示日历

## UseCase

Usecase | cmd
-- | --
显示当前日历 | `cal`
显示某月日历 | `cal x xxx`
显示 年历 | `cal xxxx`
显示本年度已经过了多少天 | `cal -j`


```
$ cal
    October 2021
Su Mo Tu We Th Fr Sa
                1  2
 3  4  5  6  7  8  9
10 11 12 13 14 15 16
17 18 19 20 21 22 23
24 25 26 27 28 29 30
31

$ cal -j
       October 2021
 Su  Mo  Tu  We  Th  Fr  Sa
                    274 275
276 277 278 279 280 281 282
283 284 285 286 287 288 289
290 291 292 293 294 295 296
297 298 299 300 301 302 303
304
```
