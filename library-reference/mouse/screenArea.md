[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# mouse.screenArea 库模块帮助文�?
## mouse 成员列表

### mouse.screenArea

屏幕选区工具

创建屏幕选区工具,

如果已打开屏幕选区则返�?null

### mouse.screenArea()

[返回对象:MouseScreenAreaObject](#MouseScreenAreaObject)

### mouse.screenArea(winform)

参数 @1 指定父窗�?
## MouseScreenAreaObject 成员列表

### MouseScreenAreaObject.close()

关闭创建屏幕选区工具

### MouseScreenAreaObject.doModal(/\*请指定所有者窗口\\n可省略此参数\*/)

此函数创建屏幕选区工具并显示为模态对话框�?
模态对话框应是独立窗口，并显示在所有者窗口前面�?
模态对话框会自己创建自己的消息循环�?
并阻止调用模态对话框的代码继续向后运�?\- 直到模态对话框被关闭�?
### MouseScreenAreaObject.onSelectionChanged

```aardio aardio
MouseScreenAreaObject.onSelectionChanged = function(rc){
    /*rc 为表示当前选区�?:RECT 结构�?/
    owner.close();
}

```

### MouseScreenAreaObject.show(false)

隐藏创建屏幕选区工具

### MouseScreenAreaObject.show(true)

显示创建屏幕选区工具

## MouseScreenAreaObject.mask 成员列表

### MouseScreenAreaObject.mask.foreground

设置遮罩颜色�?xAARRGGBB 格式数�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/mouse/screenArea.md)

