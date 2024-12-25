[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# mouse.highlighter 库模块帮助文�?
## mouse 成员列表

### mouse.highlighter

用于创建鼠标高亮光圈

创建鼠标高亮光圈

### mouse.highlighter()

[返回对象:MouseHilighterObject](#MouseHilighterObject)

### mouse.highlighter(winform,color,size,padding)

参数 @winform 指定父窗口，不可省略,

@color �?ARGB 格式颜色数值指定光圈颜色，透明度为 0 仅显示单击动画，

@size 指定光圈大小�?
@padding 指定单击鼠标动画放大缩小边距

## MouseHilighterObject 成员列表

### MouseHilighterObject.animationDuration

单击鼠标时光圈动画持续时间，以毫秒为单位

### MouseHilighterObject.animationInterval

单击鼠标时光圈动画时间间隔，以毫秒为单位

### MouseHilighterObject.changeConfig(color,size,padding)

修改光圈设置,

@color �?ARGB 格式颜色数值指定光圈颜�?

@size 指定光圈大小,

@padding 指定单击鼠标动画放大缩小边距

### MouseHilighterObject.close()

关闭窗口

### MouseHilighterObject.hwnd

窗口句柄

### MouseHilighterObject.show()

显示高亮光圈

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/mouse/highlighter.md)

