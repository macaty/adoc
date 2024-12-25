[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.util.desktop 库模块帮助文�?
## virDesktopMgrObject 成员列表

### virDesktopMgrObject.close()

关闭创建的桌�?
### virDesktopMgrObject.create("字符串参�?)

创建新桌�?
参数指定桌面名字

### virDesktopMgrObject.desktop

这是一个表对象,存储了所有虚拟桌面的名字与句�?键为桌面名字

### virDesktopMgrObject.desktop.Default

默认桌面

### virDesktopMgrObject.execute("桌面名字","程序路径","参数")

在虚拟桌面运行程�?
### virDesktopMgrObject.switch()

切换到指定名字的桌面,如果无参数则切换到前一桌面

## win.util 成员列表

### win.util.desktop()

多桌面管�?
管理 Win10/Win11 虚拟桌面请改�?dotNet.desktop

[返回对象:virDesktopMgrObject](#virDesktopMgrObject)

### 自动完成常量

\_DESKTOP\_ALL=0x1FF

\_DESKTOP\_CREATEMENU=0x4

\_DESKTOP\_CREATEWINDOW=0x2

\_DESKTOP\_ENUMERATE=0x40

\_DESKTOP\_HOOKCONTROL=0x8

\_DESKTOP\_JOURNALPLAYBACK=0x20

\_DESKTOP\_JOURNALRECORD=0x10

\_DESKTOP\_READOBJECTS=0x1

\_DESKTOP\_SWITCHDESKTOP=0x100

\_DESKTOP\_WRITEOBJECTS=0x80

\_DF\_ALLOWOTHERACCOUNTHOOK=0x1

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/util/desktop.md)

