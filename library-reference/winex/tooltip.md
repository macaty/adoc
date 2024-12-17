[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# winex.tooltip 库模块帮助文�?
## winex 成员列表

### winex.tooltip()

[返回对象:winUiTooltipObject](#winUiTooltipObject)

### winex.tooltip(ownerForm,hasCloseButton,balloon)

创建提示控件,默认使用默认手动跟踪模式�?
@ownerForm 参数指定所有者窗口，省略则默认置顶窗口，

@hasCloseButton 参数指定是否显示关闭按钮,可省略默认值为 true

@balloon 参数指定是否启用汽泡外观,可省略默认值为 true

如果未指定所有者窗口、或未设置提示标题，提示中的超链接可能无法点�?
## winex.tooltip 成员列表

创建手动控制坐标、显示的提示控件�?
只能用于界面线程

创建提示控件,默认使用默认手动跟踪模式�?
返回 win.ui.tooltip 对象

### winex.tooltip.balloon

在屏幕任意坐标显示简单气泡提示，

在提示窗口外部点击自动隐藏�?
只能用于界面线程

### winex.tooltip.balloon(false)

隐藏简单提�?
### winex.tooltip.balloon(text,x,y,timeout)

弹出简单气泡提�?@text 指定文本内容的提�?

可选用 @x,@y 参数指定显示坐标�?
不指定坐标则取鼠标当前坐�?
可选用 @timeout 参数指定超时自动关闭毫秒�?
### winex.tooltip.balloon(true,x,y,timeout)

弹出简单气泡提�?

可选用 @x,@y 参数指定显示坐标�?
不指定坐标则取鼠标当前坐�?
可选用 @timeout 参数指定超时自动关闭毫秒�?
### winex.tooltip.popup

在屏幕任意坐标显示简单提示，

在提示窗口外部点击自动隐藏�?
只能用于界面线程

### winex.tooltip.popup(false)

隐藏简单提�?
### winex.tooltip.popup(text,x,y,timeout)

弹出简单提�?@text 指定文本内容的提�?

可选用 @x,@y 参数指定显示坐标�?
不指定坐标则取鼠标当前坐�?
可选用 @timeout 参数指定超时自动关闭毫秒�?
### winex.tooltip.popup(true,x,y,timeout)

弹出简单提�?

可选用 @x,@y 参数指定显示坐标�?
不指定坐标则取鼠标当前坐�?
可选用 @timeout 参数指定超时自动关闭毫秒�?
### winex.tooltip.popupDelta(delta,x,y,timeout)

以逐步打字方式显示简单提示�?
@delta 指定要增加的文本提示，@delta �?null 结束输出�?
可选用 @x,@y 参数指定显示坐标�?
不指定坐标则取鼠标当前坐�?
可选用 @timeout 参数指定超时自动关闭毫秒数�?
已输出所有增量文本返�?true，否则返�?null �?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/winex/tooltip.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/winex/tooltip.md')

