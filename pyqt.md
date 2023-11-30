# pyqt5

## 一些参考过的仓库

[PyQt](https://github.com/PyQt5/PyQt)  #各种小控件的连接
[PyQt5-Video-Book](https://github.com/wangjx520/PyQt5-Video-Book)  #youtub上视频对应的仓库链接
[C-GIS-](https://github.com/wangjx520/C-GIS-) #大佬基于C++写的简单的GIS软件
[PVGeo](https://github.com/wangjx520/PVGeo) #基于pyvista开发的地质方面的开源软件，可以参考，但是代码估计几万行

## 将ui文件编译成py文件
```
(uran_gui) D:\WJX\code\U_mining_GUI>pyuic5 SMART_U_mining.ui -o SMART_U_mining.py
```
## 使用pyinstall库打包python工程文件为exe软件
```
(uran_gui) D:\WJX\code\U_mining_GUI>pyinstaller -Fw U_mining_main.py
```
