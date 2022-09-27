---
Title | ffmpeg
-- | --
Created @ | `2022-08-23T03:37:05Z`
Last Modify @| `2022-09-27T06:15:17Z`
Edit @| [here](https://github.com/junxnone/techwiki/issues/292)

---
## Reference
- [Remove sequentially duplicate frames when using FFmpeg](https://stackoverflow.com/questions/37088517/remove-sequentially-duplicate-frames-when-using-ffmpeg)
- [ffmpeg音视频加速](https://www.jianshu.com/p/ea4af542df6a)

## Brief


## UseCase


### 录制桌面

```
ffmpeg -f x11grab -s 2560x1440 -i :1.0 -r 25 -vcodec libx264 output.mp4
```


### 移除重复帧


```
ffmpeg -i input.mp4 -vf mpdecimate,setpts=N/FRAME_RATE/TB out.mp4
```


### 倍速视频

```
ffmpeg -i input.mp4 -an  -filter:v "setpts=0.25*PTS" output.mp4
```
- 通过修改 PTS(Presentation Time Stamp - 显示时间戳) 实现


### 制作 Gif

```
ffmpeg -i input.mp4 -r framerate output.gif
```

