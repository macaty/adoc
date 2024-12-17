[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.layered 库模块帮助文�?
## win.ui 成员列表

### win.ui.layered

创建分层窗口

支持窗体设计器指定的 png 透明背景�?背景色，

支持窗口上的 plus,bkplus 控件,其他子窗口可通过调用 orphanWindow 函数正常显示

### win.ui.layered()

[返回对象:winuilayeredObject](#winuilayeredObject)

### win.ui.layered(窗体对象,主动刷新间隔)

创建分层窗口

主动刷新间隔为可选参�?以毫秒为单位,过快会降低性能

刷新间隔设为负数可禁止主动刷�?但plus控件仍然可以自动刷新,

注意创建分层窗口以后不应再改变窗口大�?
## winuilayeredObject 成员列表

### winuilayeredObject.background

指定背景图像路径或数�?
### winuilayeredObject.backgroundColor

指定背景�?ARGB格式

### winuilayeredObject.borderRadius

指定圆角半径，仅在使定背景色时有�?
### winuilayeredObject.onDrawBackground()

```aardio aardio
winuilayeredObject.onDrawBackground = function(graphics,left,top,width,height){
    /*可以在这里继续在窗口背景上绘�?/
}

```

### winuilayeredObject.predraw()

更新窗口绘图缓存但并不立即重�?不要在onDrawBackground里调用此函数

### winuilayeredObject.redraw()

重绘窗口,不要在onDrawBackground里调用此函数

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/layered.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/layered.md')

