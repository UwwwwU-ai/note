# tkinter 的学习  

***

## 1、窗口创建、开启、设置标题  

先导入库：
`import tkinter as tk`

__创建窗口__：
`window = tk.TK()`

__设置窗口标题__：
`window.title('xxxxx')`
其中xxxx是标题名字。需要注意设置标题要在开启之前完成。  

__开启__：
`window.mainloop()`

***

## 2、窗口大小位置、获取分辨率

__获取分辨率__：
`resolution = window.maxsize()`
\# resolution 是一个元组。
`w,h = resolution`

__设置窗口大小、位置__：
`window.geometry(f'{w}x{h}')`
\# window.geometry('宽x高+距离屏幕左侧多少+距离屏幕右侧多少')
`window.geometey(f'{int(w*0.5)}x{int(h*0.5)}')`

***

## 3、窗口锁定缩放、图标

__设置窗口锁定缩放__：
`window.resizable()`
\# 传入两个bool值，其中True表示可以缩放，False表示锁定缩放。第一个位置是width，第二个位置是height
eg. `window.resizable(False,False)`

__设置窗口图标__：
`window.iconbitmap()`
\# 传入图片的路径，建议是相对路径。图片的格式是ico。

***

## 4、窗口背景、透明度设置

__设置窗口背景颜色__：
`window.configure(bg = '')`
\# 可以传入 颜色英文 以及 颜色编码
`window.configure(bg = 'red')`
`window.configure(bg = '#000000')`

__设置窗口的透明的__：
`window.attributes()`
\# 第一个位置传参 '-alpha' ，后面是数字 0-1 之间
`window.attributes('-alpha',0.5)`

***

## 5、窗口置顶、关闭函数、销毁

__窗口置顶__：
`window.attributes()`
\# 第一个位置传参 '-topmost' , 后面传入True或者False，True表示置顶，False表示不置顶
`window.attributes('-topmost',True)`

__关闭函数__：
```
window.protocol('WM_DELETE_WINDOW',close)
def close():
    print('close')
```
\# 关闭窗口时执行，需要提前创建一个函数

__销毁__：
`window.destroy()`
可以写入关闭函数中：
```
def close():
    print('close')
    window.destroy()
```

***

## 6、标签组件、填充布局

__标签组件__：
`tk.label()`
\# 需要实例化
'label = tk.label(window, text = 'xxxx', font = ('黑体',30)， fg = 'red', bg = '#000000')'

__填充布局__：
`label.pack()`

***

## 7、三种填充布局

__填充布局__：
`xx.pack()`
\# 又称默认填充，如果不设置窗口大小，标签有多大则窗口有多大

__自定义布局__：
`xx.place(x=xxxx,y=xxxx)`
\# 第一个指距离左侧有多远，第二个指距离上侧有多远

__网格布局__：
`xx.grid(row = xx,column = xx)`
\# 类似excel，第一个指的是第x行，第二个指的是第x列

***

## 8、输入框组件、字符串变量

__字符串标量__：
`str = tk.StringVar()`

__初始化设置__：
`str.set('xxxxxx')`
例如:
`str.set('Please input your email')`

__输入框组件__：
`tk.Entry(window,width = xx, textvariable = str, font = ('xx', 17), )`
相应的组件仍然可以使用三种布局。

***

## 9、字符串获取、按钮组件

__字符串获取__:
`str.get()`

__按钮组件__：
`tk.button(window, text = 'xxxx', font = ('xx' , 20), width = xx, command = function)`
\# function是相应的函数

***

## 10、四种弹窗组件

先要引入包
`from tkinter import messagebox`

蓝色：
`messagebox.showinfo(title,message)`

黄色：
`messagebox.showwarning(title,message)`

红色：
`messagebox.showerror(title,message)`

选择是否：
`messagebox.askokcancel(title,message)`
可以继续判断
```
judge = messagebox.askokcancel(title,message)
if judge:
    xxxx
else:
    xxxx
```

***

## 11、顶层窗口

顶层窗口又可以叫内层窗口，创建：
`tk.Toplevel()`
其他的组件都一致

***

## 12、补充  

state=('disabled','readonly')
`tk.Entry(window,width = xx, textvariable = str, font = ('xx', 17),state = 'disabled' )`
其中disable代表不能操作，而readonly代表只读

***

## 13、菜单创建、设置、开启

菜单创建：
`menu = tk.Menu(window)`

菜单设置：
`menu.add_cascade(label = 'xxx')`

菜单开启：
`window.config(menu)`

***

## 14、


***

## 附录A

### 1、`grid()`

`grid(row = , column = , sticky = , padx = , pady = ,)`

`row = `表示第几行
`column = `表示第几列
`sticky = `表示位置在栏位的哪里，可以填入'n'，'s'，'w'，'e'，分别表示上北下南左西右东
`padx = , pady = `表示增加上下左右的空白，单位是像素

`.rowconfigure()` `.columnconfigure()`
可以调整相应行列的所占比例。`frame.rowconfigure(row,weight = )`

***

## 附录B

### 1、容器

`tk.TK()` `tk.Frame()` `tk.Toplevel()`

