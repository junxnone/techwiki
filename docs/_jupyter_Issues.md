---
Title |  jupyter Issues
-- | --
Create Date | `2021-09-22T09:08:28Z`
Update Date | `2021-09-22T09:08:28Z`
Edit link | [here](https://github.com/junxnone/linuxwiki/issues/144)

---
# Reference
- [ImportError: cannot import name 'create_prompt_application'](https://blog.csdn.net/qq_33716688/article/details/84630679)
- [OpenCV | imshow()弹出窗口图片未响应；无法显示图片](https://blog.csdn.net/yefcion/article/details/79435591)

## **Issues 1 `jupyter 启动没问题，但是当打开页面运行时会报如下错误`：**


```
Traceback (most recent call last):
  File "/usr/lib/python3.6/runpy.py", line 193, in _run_module_as_main
    "__main__", mod_spec)
  File "/usr/lib/python3.6/runpy.py", line 85, in _run_code
    exec(code, run_globals)
  File "/home/xxx/.local/lib/python3.6/site-packages/ipykernel_launcher.py", line 15, in <module>
    from ipykernel import kernelapp as app
  File "/home/xxx/.local/lib/python3.6/site-packages/ipykernel/__init__.py", line 2, in <module>
    from .connect import *
  File "/home/xxx/.local/lib/python3.6/site-packages/ipykernel/connect.py", line 13, in <module>
    from IPython.core.profiledir import ProfileDir
  File "/usr/lib/python3/dist-packages/IPython/__init__.py", line 49, in <module>
    from .terminal.embed import embed
  File "/usr/lib/python3/dist-packages/IPython/terminal/embed.py", line 18, in <module>
    from IPython.terminal.interactiveshell import TerminalInteractiveShell
  File "/usr/lib/python3/dist-packages/IPython/terminal/interactiveshell.py", line 20, in <module>
    from prompt_toolkit.shortcuts import create_prompt_application, create_eventloop, create_prompt_layout, create_output
ImportError: cannot import name 'create_prompt_application'

```

### Solution
```
sudo -E pip3 install  prompt-toolkit==1.0.16
```


## **Issue 2 安装tensorflow docker 后 jupyter 只支持python2**

- **pull tensorflow docker py3**

## **Issue 3 jupyter tables 会被居中显示**

![image](https://user-images.githubusercontent.com/2216970/71860969-9b7b6280-312f-11ea-9303-a55cf732ed94.png)

在之前执行html table style 设置
```
%%html
<style>
table {float:left}
</style>
```
![image](https://user-images.githubusercontent.com/2216970/71860985-aa621500-312f-11ea-9d61-2ba33549d833.png)

> Google Colab not support html tags

## **Issue 4 其他文件的 `module` 修改了但是执行时未更改**

- 需要重启并执行全部(类似于之前的 `module` 已经载入在内存中了)

## **Issue 5 cv2.imshow() not working with Jupyter**
imshow后需要添加如下内容，且 必须按任意按键退出不能点 X 退出。

```
cv2.waitKey()
cv2.destroyAllWindows()
```

