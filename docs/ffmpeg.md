---
Title | ffmpeg
-- | --
Created @ | `2022-08-23T03:37:05Z`
Last Modify @| `2022-08-23T03:37:05Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/292)

---
## Reference

## Brief


## UseCase

### 移除重复帧


```
#ffmpeg -i input.mp4 -vf mpdecimate,setpts=N/FRAME_RATE/TB out.mp4
```
