---
Title | Linux image2string
-- | --
Create Date | `2021-09-22T02:32:49Z`
Update Date | `2021-09-22T02:32:49Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/78)

---
# Brief
- 远程 `shell` 查看图片可以把图片转成字符串形式
- Tools
  - asciiview 
  - cacaview 
  - img2txt 

## asciiview 

- **Install**

```
sudo apt-get install aview imagemagick
```

- **Control Hotkey**

```
       a,w,d,x               Move the image one row/column.
       A,W,D,X              Move the image one page.
       Z,+    Zoom in.
       z,-    Zoom out.
       s      Save image.
       m      Change dithering mode.
       q      Quit the viewer.
       i      Turn inversion on.
       I      Turn inversion off.
       u      Select attributes.
       f      Select font.
       SPACE  Redraw screen.
       .      Increase contrast (dot).
       ,      Decrease contrast (comma).
       '      Increase gamma (single quote).
       ;      Decrease gamma (semicolon).
       >      Increase brightness.
       <      Decrease brightness.
```

### UseCase

- **查看转码后的效果**

```
asciiview your_image.png
```
- 按 `s` 保存时可以调整 width 和 height 调整输出 宽高
> 太大会无法正常显示

- **去掉前后的空格**

```
sed 's/^[ ].\{40\}//g;s/[ ].\{40\}$//g' your_output.txt 
```

## cacaview 

- **Install caca-utils**

```
sudo apt install caca-utils
```

- **cacaview 查看图片**

```
cacaview xxxx.png
```

- **cacaview 查看文件夹**

```
cacaview data/image/*
```

