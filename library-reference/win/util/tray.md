[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.util.tray 库模块帮助文�?
## win.util 成员列表

### win.util.tray

创建托盘图标

### win.util.tray()

[返回对象:winUtilTrayObject](#winUtilTrayObject)

### win.util.tray(主窗�?图标,提示信息)

创建托盘图标,必须指定窗体对象�?
图标参数可指定图标ID、句柄、图标数据或图标路径，默认为窗体图标�?
提示信息：鼠标移到托盘图标上提示的信�?省略则没有提示信�?
## winUtilTrayObject 成员列表

### winUtilTrayObject.delete()

删除托盘图标

如果指定了图标数据或路径则必须在不需要托盘图标时调用delete函数释放

### winUtilTrayObject.icon

用于设置托盘图标,只写属性�?
属性值可以是图标ID、句柄、图标数据或图标路径,

32位图�?最好同时提�?16x16�?2x32 的复合图�?
如果传入的是需要释放的图标句柄请改�?setIcon 函数

### winUtilTrayObject.message

指定回调消息

当用户点击托盘图标时、向主窗体发送此消息

### winUtilTrayObject.pop

发送托盘消息通知�?
Win10 以下显示为汽泡提示，

Win10 开始由操作系统的『专注』、应用程序的『通知』等设置决定是否显示模幅提示或折叠消息到通知区�?
Win10/11 获取通知消息可使�?dotNet.toastListener 扩展库�?
### winUtilTrayObject.pop(提示信息,标题,图标ID,显示超时)

发送托盘消息通知�?
图标 ID 可省略，警告图标设为2,错误图标设为3

显示超时以秒为单�?
### winUtilTrayObject.reset()

重置并恢复托盘图�?
### winUtilTrayObject.setIcon()

设置托盘的图�?

参数@1可以是图标ID、句柄、图标数据或图标路径,

32位图�?最好同时提�?16x16�?2x32 的复合图�?
如果指定需要释放的图标句柄，参数@2 应设�?true

### winUtilTrayObject.tip

设置鼠标提示信息

### 自动完成常量

\_NIIF\_ERROR=3

\_NIIF\_ICON\_MASK=0xF

\_NIIF\_INFO=1

\_NIIF\_NOSOUND=0x10

\_NIIF\_WARNING=2

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/util/tray.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/util/tray.md')

