# tkinter 的学习  

***

## 1、窗口创建、开启、设置标题  

先导入库：
`import tkinter as tk`

创建窗口：
`a = tk.TK()`

设置窗口标题：
`a.title('xxxxx')`
其中xxxx是标题名字。需要注意设置标题要在开启之前完成。  

开启：
`a.mainloop()`

***

## 2、窗口大小位置、获取分辨率

获取分辨率：
`resolution = a.maxsize()`
\# resolution 是一个元组。
`w,h = resolution`

设置窗口大小、位置：
`a.geometry(f'{w}x{h}')`
\# a.geometry('宽x高+距离屏幕左侧多少+距离屏幕右侧多少')
`a.geometey(f'{int(w*0.5)}x{int(h*0.5)}')`

***

## 3、窗口锁定缩放、图标

设置窗口锁定缩放：
`a.resizable()`
\# 传入两个bool值，其中True表示可以缩放，False表示锁定缩放。第一个位置是width，第二个位置是height
eg. `a.resizable(False,False)`

设置窗口图标：
`a.iconbitmap()`
\# 传入图片的路径，建议是相对路径。图片的格式是ico。

***

## 4、窗口背景、透明度设置

设置窗口背景颜色：
`a.configure(bg = '')`
\# 可以传入 颜色英文 以及 颜色编码
`a.configure(bg = 'red')`
`a.configure(bg = '#000000')`

设置窗口的透明的：
`a.attributes()`
\# 第一个位置传参 '-alpha' ，后面是数字 0-1 之间
`a.attributes('-alpha',0.5)`

***

## 5、窗口置顶、关闭函数、销毁

窗口置顶：
`a.attributes()`
\# 第一个位置传参 '-topmost' , 后面传入True或者False，True表示置顶，False表示不置顶
`a.attributes('-topmost',True)`

关闭函数：
```
a.protocol('WM_DELETE_WINDOW',close)
def close():
    print('close')
```
\# 关闭窗口时执行，需要提前创建一个函数

销毁：
`a.destroy()`
可以写入关闭函数中：
```
def close():
    print('close')
    a.destroy()
```
