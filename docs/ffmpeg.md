---
Title | ffmpeg
-- | --
Created @ | `2022-08-23T03:37:05Z`
Last Modify @| `2022-08-23T03:41:29Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/292)

---
## Reference
- [Remove sequentially duplicate frames when using FFmpeg](https://stackoverflow.com/questions/37088517/remove-sequentially-duplicate-frames-when-using-ffmpeg)


## Brief


## UseCase

### 移除重复帧


```
ffmpeg -i input.mp4 -vf mpdecimate,setpts=N/FRAME_RATE/TB out.mp4
```
