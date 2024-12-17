[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.util.changeNotification 库模块帮助文�?
## win.util 成员列表

### win.util.changeNotification

监听用户对资源管理器的操�?
### win.util.changeNotification()

[返回对象:wuChangeNotificationObject](#wuChangeNotificationObject)

### win.util.changeNotification(窗口对象)

注册文件监听窗口\\监听用户对资源管理器的操�?

省略参数则创�?message only window

## wuChangeNotificationObject 成员列表

### wuChangeNotificationObject.\_form

[返回对象:winform](../ui/_.html#winform)

### wuChangeNotificationObject.clear()

清空所有监视路径并停止监视目录，返回对象自�?
[返回对象:wuChangeNotificationObject](#wuChangeNotificationObject)

### wuChangeNotificationObject.deregister()

注销并关闭文件监�?
### wuChangeNotificationObject.onAssocChanged

```aardio aardio
wuChangeNotificationObject.onAssocChanged = function(srcPath,dstPath){
    _/*文件关联被改变了*/
}

```

### wuChangeNotificationObject.onAttributes

```aardio aardio
wuChangeNotificationObject.onAttributes = function(srcPath,dstPath){
    /*文件属性被改变*/
}

```

### wuChangeNotificationObject.onCreate

```aardio aardio
wuChangeNotificationObject.onCreate = function(srcPath,dstPath){
    /*文件夹的外壳成员创建�?/
}

```

### wuChangeNotificationObject.onDelete

```aardio aardio
wuChangeNotificationObject.onDelete = function(srcPath,dstPath){
    /*非文件夹的外壳成员删除了*/
}

```

### wuChangeNotificationObject.onDriveAdd

```aardio aardio
wuChangeNotificationObject.onDriveAdd = function(srcPath,dstPath){
    /*添加了驱动器*/
}

```

### wuChangeNotificationObject.onDriveAddGui

```aardio aardio
wuChangeNotificationObject.onDriveAddGui = function(srcPath,dstPath){
    /*通过外壳添加的驱动器*/
}

```

### wuChangeNotificationObject.onDriveRemoved

```aardio aardio
wuChangeNotificationObject.onDriveRemoved = function(srcPath,dstPath){
    /*驱动器被删除�?/
}

```

### wuChangeNotificationObject.onFreeSpace

```aardio aardio
wuChangeNotificationObject.onFreeSpace = function(srcPath,dstPath){
    /*驱动器剩余空间数变化*/
}

```

### wuChangeNotificationObject.onMakeDir

```aardio aardio
wuChangeNotificationObject.onMakeDir = function(srcPath,dstPath){
    /*目录被创�?/
}

```

### wuChangeNotificationObject.onMediaInserted

```aardio aardio
wuChangeNotificationObject.onMediaInserted = function(srcPath,dstPath){
    /*存储介质被插�?/
}

```

### wuChangeNotificationObject.onMediaRemoved

```aardio aardio
wuChangeNotificationObject.onMediaRemoved = function(srcPath,dstPath){
    /*存储介质被删�?/
}

```

### wuChangeNotificationObject.onNetShare

```aardio aardio
wuChangeNotificationObject.onNetShare = function(srcPath,dstPath){
    /*本地的目录被共享*/
}

```

### wuChangeNotificationObject.onNetUnShare

```aardio aardio
wuChangeNotificationObject.onNetShare = function(srcPath,dstPath){
    /*本地的目录取消共�?/
}

```

### wuChangeNotificationObject.onRemoveDir

```aardio aardio
wuChangeNotificationObject.onRemoveDir = function(srcPath,dstPath){
    /*文件夹中的内容被改变*/
}

```

### wuChangeNotificationObject.onRenameFolder

```aardio aardio
wuChangeNotificationObject.onRenameFolder = function(srcPath,dstPath){
    /*文件夹名称被改变*/
}

```

### wuChangeNotificationObject.onRenameItem

```aardio aardio
wuChangeNotificationObject.onRenameItem = function(srcPath,dstPath){
    /*非文件外壳对象名称被改变*/
}

```

### wuChangeNotificationObject.onSeverDisconnect

```aardio aardio
wuChangeNotificationObject.onSeverDisconnect = function(srcPath,dstPath){
    /*计算机被服务器断开*/
}

```

### wuChangeNotificationObject.onUpdateDir

```aardio aardio
wuChangeNotificationObject.onUpdateDir = function(srcPath,dstPath){
    /*文件夹中的内容被改变
此目录下的较多文件变更可能被合并为此事件*/
}

```

### wuChangeNotificationObject.onUpdateImage

```aardio aardio
wuChangeNotificationObject.onUpdateImage = function(srcPath,dstPath){
    /*系统图像列表中的图像被改�?/
}

```

### wuChangeNotificationObject.onUpdateItem

```aardio aardio
wuChangeNotificationObject.onUpdateItem = function(srcPath,dstPath){
    /*非文件夹外壳对象的名称被改变*/
}

```

### wuChangeNotificationObject.register(自定义消�?选项)

注册并启用文件监视功�?

所有参数都可以省略,默认使用 \_WM\_USERDEF\_FILECHANGED 消息

调用此函数以�?必须指定所有需要启用的事件回调函数

### wuChangeNotificationObject.watch()

[返回对象:wuChangeNotificationObject](#wuChangeNotificationObject)

### wuChangeNotificationObject.watch(监视路径,是否监视子目�?

添加监视路径,路径可以使用\_CSIDL\_开头的常量表示

参数2为可选参�?返回对象自身

### 自动完成常量

\_SHCNEE\_MSI\_CHANGE=4

\_SHCNEE\_MSI\_UNINSTALL=5

\_SHCNEE\_ORDERCHANGED=2

\_SHCNE\_ALLEVENTS=0x7FFFFFFF

\_SHCNE\_ASSOCCHANGED=0x8000000

\_SHCNE\_ATTRIBUTES=0x800

\_SHCNE\_CREATE=2

\_SHCNE\_DELETE=4

\_SHCNE\_DISKEVENTS=0x2381F

\_SHCNE\_DRIVEADD=0x100

\_SHCNE\_DRIVEADDGUI=0x10000

\_SHCNE\_DRIVEREMOVED=0x80

\_SHCNE\_FREESPACE=0x40000

\_SHCNE\_GLOBALEVENTS=0xC0581E0

\_SHCNE\_INTERRUPT=0x80000000

\_SHCNE\_MEDIAINSERTED=0x20

\_SHCNE\_MEDIAREMOVED=0x40

\_SHCNE\_MKDIR=8

\_SHCNE\_NETSHARE=0x200

\_SHCNE\_NETUNSHARE=0x400

\_SHCNE\_RENAMEFOLDER=0x20000

\_SHCNE\_RENAMEITEM=1

\_SHCNE\_RMDIR=0x10

\_SHCNE\_SERVERDISCONNECT=0x4000

\_SHCNE\_UPDATEDIR=0x1000

\_SHCNE\_UPDATEIMAGE=0x8000

\_SHCNE\_UPDATEITEM=0x2000

\_SHCNF\_DWORD=3

\_SHCNF\_FLUSH=0x1000

\_SHCNF\_FLUSHNOWAIT=0x3000

\_SHCNF\_IDLIST=0

\_SHCNF\_NOTIFYRECURSIVE=0x10000

\_SHCNF\_PRINTER=2

\_SHCNF\_TYPE=0xFF

\_SHCNF\_srcPath=5

\_SHCNRF\_InterruptLevel=1

\_SHCNRF\_NewDelivery=0x8000

\_SHCNRF\_RecursiveInterrupt=0x1000

\_SHCNRF\_ShellLevel=2

\_WM\_USERDEF\_FILECHANGED=0x8F00

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/util/changeNotification.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/util/changeNotification.md')

