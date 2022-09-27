---
Title | ffmpeg
-- | --
Created @ | `2022-08-23T03:37:05Z`
Last Modify @| `2022-09-27T03:07:00Z`
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

### 录制桌面

```
ffmpeg -f x11grab -s 2560x1440 -i :1.0 -r 25 -vcodec libx264 output.mp4
```

### 制作 Gif

```
ffmpeg -i input.mp4 -r framerate output.gif
```
