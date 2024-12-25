[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.appBar 库模块帮助文�?
## win 成员列表

### win.appBar()

[返回对象:winAppBarObject](#winAppBarObject)

### win.appBar(句柄)

可选指定句�?

可选在第二个参数中使用表对象指定APPBARDATA属�?
## win.appBar 成员列表

任务�?
### win.appBar.autoHide( 任务栏句�?false)

取消自动隐藏

### win.appBar.autoHide( 任务栏句�?true)

设置为自动隐�?
### win.appBar.command()

发送命�?

参数@1指定命令 ID，参数为 419 可显示桌面�?
### win.appBar.find()

返回系统任务栏句�?
### win.appBar.getAutoHideBar()

返回�?�?�?下四个被设置为自动隐藏的任务栏句�?
### win.appBar.getTaskBar()

返回系统任务栏信�?失败返回null

[返回对象:STDAPPBARDATAObject](#STDAPPBARDATAObject)

### win.appBar.isAutoHide( 任务栏句�?)

任务栏是否自动隐�?
### win.appBar.message(\_ABM,{} )

发送任务栏命令,

可选在第二个参数中使用一个表对象指定 APPBARDATA 的部分字段�?
函数会自动创�?APPBARDATA 结构体，并且合并参数 @2 指定的字段值�?
### win.appBar.regist

将窗口注册接收任务栏通知消息�?
相关范例: [https://www.aardio.com/zh-cn/doc/example/System/Desktop/appBarMsg.html](https://www.aardio.com/zh-cn/doc/example/System/Desktop/appBarMsg.html)

### win.appBar.regist(窗口句柄,自定义回调消息ID)

将窗口注册接收任务栏通知消息�?
请在参数 @1 指定的窗口接收参�?@2 指定的消�?ID�?
wParam 为通知代码，例如应用全屏事件通知代码�?\_ABN\_FULLSCREENAPP

lParam 为通知参数，对�?\_ABN\_FULLSCREENAPP 表示是否全屏

### win.appBar.regist(窗口对象,通知回调函数)

```aardio aardio
win.appBar.regist(winform,function(code,param){
    if(code == 2/*_ABN_FULLSCREENAPP*/){
        /*code 为通知代码，param 为通知参数�?对于 _ABN_FULLSCREENAPP 通知消息 ，param 为是否有全屏窗口*/
    }
})

```

### win.appBar.setAutoHideBar( 任务栏句�?\_ABE\_BOTTOM )

设置为自动停�?
### win.appBar.unRegist(窗口句柄)

取消注册的任务栏回调消息

## STDAPPBARDATAObject 成员列表

### STDAPPBARDATAObject.hwnd

窗口句柄

### STDAPPBARDATAObject.rc

屏幕区块位置

### STDAPPBARDATAObject.rc.bottom

�?
### STDAPPBARDATAObject.rc.left

�?
### STDAPPBARDATAObject.rc.right

�?
### STDAPPBARDATAObject.rc.top

�?
### STDAPPBARDATAObject.state

状�?
_ABS_ 前缀常量

### STDAPPBARDATAObject.uEdge

状态栏靠在屏幕哪个�?
_ABE_ 前缀常量

### 自动完成常量

\_ABE\_BOTTOM=0x3

\_ABE\_LEFT=0x0

\_ABE\_RIGHT=0x2

\_ABE\_TOP=0x1

\_ABM\_ACTIVATE=0x6

\_ABM\_GETAUTOHIDEBAR=0x7

\_ABM\_GETSTATE=0x4

\_ABM\_GETTASKBARPOS=0x5

\_ABM\_NEW=0x0

\_ABM\_QUERYPOS=0x2

\_ABM\_REMOVE=0x1

\_ABM\_SETAUTOHIDEBAR=0x8

\_ABM\_SETPOS=0x3

\_ABM\_SETSTATE=0xA

\_ABM\_WINDOWPOSCHANGED=0x9

\_ABN\_FULLSCREENAPP=2

\_ABN\_POSCHANGED=1

\_ABN\_STATECHANGE=0

\_ABN\_WINDOWARRANGE=3

\_ABS\_ALWAYSONTOP=0x2

\_ABS\_AUTOHIDE=0x1

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/appBar.md)

