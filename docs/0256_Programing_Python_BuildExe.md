---
Title | Programing Python BuildExe
-- | --
Created @ | `2019-09-17T03:30:34Z`
Last Modify @| `2022-12-22T06:32:49Z`
Labels | ``
Edit @| [here](https://github.com/junxnone/techwiki/issues/256)

---
# 编译可执行文件

## Reference
- [如何将Python脚本打包成可执行文件？](https://ningyu1.github.io/site/post/59-py2exe-pyinstaller/)
- [pyinstaller 官网](http://www.pyinstaller.org/)
- [Python PyInstaller安装和使用教程](http://c.biancheng.net/view/2690.html)
- [打包错误；pyinstaller；No module named 'sklearn.utils._cython_blas'](https://juejin.im/post/6844904113642143758)
- [Nuitka命令选项参数帮助](http://mrdoc.zmister.com/project-53/doc-265/)

## Brief
- 把 Python 应用编译成可执行文件或库
- Tools `cython/pyinstaller/distutils/Nuitka`
  - cython 生成 so 库
  - pyinstaller/Nuitka 生成可执行文件
  - distutils 生成 pyd 扩展模块

## 使用 nuitka 生成可执行文件
- 可以部分使用外部环境

```
pip3 install nuitka
```

Target | Commad
-- | --
生成可执行文件 | `python -m nuitka test.py -o test`
包含本地 `module` | `python -m nuitka demo.py -o demo --include-module=utils,tools

# 使用 `cython` 生产 `so` 库
- 安装 cython

```
pip3 install cython
```

- 编写 setup.py

```
# setup.py
from distutils.core import setup
from Cython.Build import cythonize

setup(ext_modules = cythonize(["test.py"]))
```

- 编译

```
python3 setup.py build_ext
```

```
$ tree build/
build/
├── lib.linux-x86_64-3.6
│   └── test.cpython-36m-x86_64-linux-gnu.so
└── temp.linux-x86_64-3.6
    └── test.o
```

## 使用 `pyinstaller` 生成可执行文件
- 安装 pyinstaller

```
pip3 install pyinstaller
```

- 生成可执行文件

```
pyinstaller test.py
```

- 测试可执行文件

```
dist/test$ ./test -h
usage: test [-h] --input_dir INPUT_DIR --output_dir OUTPUT_DIR

optional arguments:
  -h, --help            show this help message and exit
  --input_dir INPUT_DIR, -i INPUT_DIR
                        The input directory for good origin image
  --output_dir OUTPUT_DIR, -o OUTPUT_DIR
                        The output directory for generated mask
```

可能的报错
Issues | Solution
-- | --
No module named 'distutils' | [distutils](https://blog.csdn.net/MacwinWin/article/details/88242432)  and [ pyinstaller distutils issues](https://github.com/pyinstaller/pyinstaller/issues/4064)
No module named 'sklearn.utils._cython_blas' | `--hidden-import="sklearn.utils._cython_blas" `
不能读取 相对路径下的 `config` 文件 | [os.path.realpath(__file__)](https://blog.csdn.net/weixin_33670786/article/details/92267914)
