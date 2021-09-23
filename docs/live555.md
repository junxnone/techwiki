---
Title | live555
-- | --
Create Date | `2021-09-23T03:31:41Z`
Update Date | `2021-09-23T03:31:41Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/164)

---
# Reference
- [live555-latest.tar.gz](http://www.live555.com/liveMedia/public/live555-latest.tar.gz)
- [test_stream.264](https://media.githubusercontent.com/media/Intel-Media-SDK/MediaSDK/master/tests/content/test_stream.264) 

# Brief
- rtsp mediaServer

## Build

```
wget http://www.live555.com/liveMedia/public/live555-latest.tar.gz
tar zvxf live555-latest.tar.gz
cd live
./genMakefiles linux
make
```

## Test
copy the test.264 file to mediaServer folder
```
cd mediaServer
./live555MediaServer
```
Test tools
- opencv #185 
- vlc **sudo apt install vlc**
- Android Phone MX player

## Support format

```
	".264" => a H.264 Video Elementary Stream file
	".265" => a H.265 Video Elementary Stream file
	".aac" => an AAC Audio (ADTS format) file
	".ac3" => an AC-3 Audio file
	".amr" => an AMR Audio file
	".dv" => a DV Video file
	".m4e" => a MPEG-4 Video Elementary Stream file
	".mkv" => a Matroska audio+video+(optional)subtitles file
	".mp3" => a MPEG-1 or 2 Audio file
	".mpg" => a MPEG-1 or 2 Program Stream (audio+video) file
	".ogg" or ".ogv" or ".opus" => an Ogg audio and/or video file
	".ts" => a MPEG Transport Stream file
		(a ".tsx" index file - if present - provides server 'trick play' support)
	".vob" => a VOB (MPEG-2 video with AC-3 audio) file
	".wav" => a WAV Audio file
	".webm" => a WebM audio(Vorbis)+video(VP8) file
```
