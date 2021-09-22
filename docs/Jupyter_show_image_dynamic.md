---
Title | Jupyter show image dynamic
-- | --
Create Date | `2021-09-22T09:04:45Z`
Update Date | `2021-09-22T09:04:45Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/139)

---
# Reference
- [如何在jupyter notebook中播放视频（不停地展示图片）](https://blog.csdn.net/BlowfishKing/article/details/81502432)

# 使用 ipython.display.display

```
from IPython.display import clear_output, Image, display
import base64
import time

def show_img(image):
    clear_output(wait=True)
    ret, png = cv2.imencode('.png', image)
    time.sleep(0.02)
    display(Image(data=png))
```
