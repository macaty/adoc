[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.util.deviceNotification 库模块帮助文�?
## win.util 成员列表

### win.util.deviceNotification

设备检�?
### win.util.deviceNotification()

[返回对象:winDeviceNotificationObject](#winDeviceNotificationObject)

### win.util.deviceNotification(输入winform对象)

创建一个设备通知窗口

在添加或移除设备时可响应通知消息

可选使用参数@2指定GUID

## winDeviceNotificationObject 成员列表

### winDeviceNotificationObject.onDeviceArrival

```aardio aardio
winDeviceNotificationObject.onDeviceArrival = function(devType,devData,pDevData){
    if( devType == 2/*_DBT_DEVTYP_VOLUME*/ ){
        if( devData.isMedia ){
            io.print("插入光盘",devData.drives[1] )
        }
        elseif( devData.isNet ){
            io.print("添加网络�?,devData.drives[1])
        }
        else {
            io.print("添加磁盘",devData.drives[1])
        }
    }
}

```

### winDeviceNotificationObject.onDeviceQueryRemove

```aardio aardio
winDeviceNotificationObject.onDeviceQueryRemove = function(devType,devData,pDevData){

}

```

### winDeviceNotificationObject.onDeviceQueryRemoveFailed

```aardio aardio
winDeviceNotificationObject.onDeviceQueryRemoveFailed = function(devType,devData,pDevData){

}

```

### winDeviceNotificationObject.onDeviceRemoveComplete

```aardio aardio
winDeviceNotificationObject.onDeviceRemoveComplete = function(devType,devData,pDevData){
    if( devType == 2/*_DBT_DEVTYP_VOLUME*/ ){
        if( devData.isUsbDevice ){
            io.print("移除U�?,devData.drives[1])
        }
    }
}

```

### winDeviceNotificationObject.onDeviceRemovePending

```aardio aardio
winDeviceNotificationObject.onDeviceRemovePending = function(devType,devData,pDevData){

}

```

### winDeviceNotificationObject.onDeviceTypeSpecific

```aardio aardio
winDeviceNotificationObject.onDeviceTypeSpecific = function(devType,devData,pDevData){

}

```

### winDeviceNotificationObject.onVolumeArrival

```aardio aardio
winDeviceNotificationObject.onVolumeArrival = function(devData,pDevData){
    if( devData.isMedia ){
        io.print("插入光盘",devData.drives[1] )
    }
    elseif( devData.isNet ){
        io.print("添加网络�?,devData.drives[1])
    }
    elseif(sys.storage.isUsbDevice(devData.drives[1])){
        io.print("插入U�?,devData.drives[1] )
    }
}

```

### winDeviceNotificationObject.onVolumeRemoveComplete

```aardio aardio
winDeviceNotificationObject.onVolumeRemoveComplete = function(devData,pDevData){
    io.print("移除�?,devData.drives[1])
}

```

### 自动完成常量

\_BROADCAST\_QUERY\_DENY=0x424D5144

\_DBT\_DEVICEARRIVAL=0x8000

\_DBT\_DEVICEQUERYREMOVE=0x8001

\_DBT\_DEVICEQUERYREMOVEFAILED=0x8002

\_DBT\_DEVICEREMOVECOMPLETE=0x8004

\_DBT\_DEVICEREMOVEPENDING=0x8003

\_DBT\_DEVICETYPESPECIFIC=0x8005

\_DBT\_DEVTYP\_DEVICEINTERFACE=5

\_DBT\_DEVTYP\_DEVINST=7

\_DBT\_DEVTYP\_DEVNODE=1

\_DBT\_DEVTYP\_HANDLE=6

\_DBT\_DEVTYP\_NET=4

\_DBT\_DEVTYP\_OEM=0

\_DBT\_DEVTYP\_PORT=3

\_DBT\_DEVTYP\_VOLUME=2

\_WM\_DEVICECHANGE=0x0219

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/util/deviceNotification.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/util/deviceNotification.md')

