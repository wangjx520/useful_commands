```py
from distutils.core import setup #用于构建和安装python包

from Cython.Build import cythonize #用于将Cython代码编译成C扩展模块

setup(ext_modules = cythonize(["pyvista_curves.py"])) 
```
使用Cython将指定的python模块(pyvista_curve.py)编译成C扩展模块，并使用
distutils进行安装和构建，可以提高代码的执行效率。

1. 建立setup.py文件，文件内容为以上三行代码
2. 在终端执行```python setup.py build_ext --inplace```
3. 将得到的同级目录(inplace关键字保证同级目录)下的.pyd扩展文件改为py文件相同的名字
4. 将原本的py文件删除