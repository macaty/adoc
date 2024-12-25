[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.util.popup 库模块帮助文�?
## utilpopupObject 成员列表

### utilpopupObject.countdown

```aardio aardio
utilpopupObject.countdown=function(remaintime){
    ..io.print("剩余时间�?,remaintime  + "�?)
}

```

## win.util 成员列表

### win.util.popup()

[返回对象:utilpopupObject](#utilpopupObject)

### win.util.popup(winform对象,显示超时,点击是否关闭,屏幕右侧边距,移动速度,移动步进)

创建一个通知窗口,在屏幕右下角弹出

除参数一以外,所有参数可�?

显示延时: 以毫秒为单位,延时�?1表示一直显�?
点击是否关闭: 为true则在显示超时以后点击窗口范围外时关闭自身

移动速度:每次向上移动显示的间�?以毫秒为单位

移动步进:每次向上移动的距�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/util/popup.md)

