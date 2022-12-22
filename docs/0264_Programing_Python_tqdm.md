---
Title | Programing Python tqdm
-- | --
Created @ | `2019-07-19T06:22:40Z`
Last Modify @| `2022-12-22T06:40:07Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/264)

---
## Reference

- [Github - tqdm](https://github.com/tqdm/tqdm)
- [tqdm==>python可扩展进度条](https://blog.csdn.net/xiaodongxiexie/article/details/70495618)
- [Docs](https://tqdm.github.io/)

## Brief
- 进度条工具
- Modules
  - tqdm.trange
  - tqdm.tqdm
- 也可以在命令行中使用

## UseCase

UseCase | Description
-- | --
tqdm.trange() | `for i in trange(100):`
tqdm.tqdm() | `for char in tqdm(list):`<br>`for image, label in tqdm(train_dataloader):`
在jupyter notebook 中使用 | `from tqdm.notebook import trange, tqdm`
进度条跑完后清除进度条 | 设置 `leave = False` <br>`pbar = trange(100, leave=False)`
在进度条上面显示log | `pbar.clear()`<br>`print(your info)`<br>`pbar.set_description(pbar info)`
在 shell 中使用 | `cat *.txt \| python3 -m tqdm --unit loc --unit_scale --total 1075075 \| wc -l`


### tenumerate

```
from tqdm.contrib import tenumerate
...
for batch_idx,(images,target) in tenumerate(train_queue):
  ... 
  tqdm.auto.tqdm.write(f"batch:{batch_idx:03d} - loss:{loss.item():.5} - time:{time_consuming:.3} sec")
```

### multi-processing

```
p = Pool(initializer=tqdm.set_lock, initargs=(tqdm.get_lock(), ))

for _ in tqdm(p.imap(fun, data_list), total=len(data_list)):
  pass
```



