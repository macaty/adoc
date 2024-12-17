[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# sys.power.notification 库模块帮助文�?
## sys.power 成员列表

### sys.power.notification

用于注册接收电源设置或状态变更事件的通知窗体

注册接收电源设置或状态变更事件的通知窗口�?
相关文档�?[https://docs.microsoft.com/en-us/windows/win32/power/power-setting-guids](javascript:if(confirm('https://docs.microsoft.com/en-us/windows/win32/power/power-setting-guids  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://docs.microsoft.com/en-us/windows/win32/power/power-setting-guids')

### sys.power.notification()

[返回对象:sysPowerNotificationObject](#sysPowerNotificationObject)

### sys.power.notification(winform,guid,dataStruct)

参数 @winform 必须指定父窗�?

参数 @guid 可用字符串或 win.guid 对象指定事件 GUID�?
可选用参数 @dataStruct 指定解析回调参数值的结构体�?
如果结构体包�?value 字段，则回调参数值为 value 字段值�?
不指�?@dataStruct 则默认为 {INT value}

## sysPowerNotificationObject 成员列表

### sysPowerNotificationObject.onPowerResuming

```aardio aardio
onPowerResuming = function(automatic){
    /*自低耗电恢复触发此事件，
系统自动恢复�?automatic 参数�?true�?用户操作恢复则在数为 false*/
}

```

### sysPowerNotificationObject.onPowerSettingChange

```aardio aardio
onPowerSettingChange = function(guid,data){
    /*电源设置或设置状态变更，
参数�?guid 为设�?GUID�?data 为参数�?/
}

```

### sysPowerNotificationObject.onPowerStatusChange

```aardio aardio
onPowerStatusChange = function(systemPowerStatus){
    /*电源状态变更，
参数�?SYSTEM_POWER_STATUS 结构体，
请参考该结构体相关资�?/
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/power/notification.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/power/notification.md')

