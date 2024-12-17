[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.accelerator 库模块帮助文�?
## win.ui 成员列表

### win.ui.accelerator

快捷�?
在绑定的窗体范围内有�?
### win.ui.accelerator()

[返回对象:winUiAcceleratorObject](#winUiAcceleratorObject)

### win.ui.accelerator(accTable,winform)

```aardio aardio
//每个窗体仅能绑定快捷键表一次，
//绑定后将会重定义窗体的preTranslateAccelerator事件用于响应快捷�?win.ui.accelerator({
    { ctrl = true; vkey = 'N'#; oncommand = function(id,event){ } }
    { ctrl = true; vkey = 'O'#; cmd = /*可以用cmd指定消息ID，或使用oncommand指定一个消息处理函�?/ }
},winform);

```

## winUiAcceleratorObject 成员列表

### winUiAcceleratorObject.destroy()

删除此快捷键对象

此函数在窗体关闭时将被自动调�?
### winUiAcceleratorObject.translate(msg.hwnd)

可用于重定义窗体的preTranslateAccelerator事件时响应快捷键使之生效

msg为preTranslateAccelerator事件的消息参�?hwnd一般应该省�?
也可以在子窗体中响应父窗体的快捷�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/accelerator.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/accelerator.md')

