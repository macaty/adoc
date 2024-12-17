[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.wlan 库模块帮助文�?
## sys 成员列表

### sys.wlan

无线网络

### sys.wlan()

创建无线网络操作对象

[返回对象:SysWlanObject](#SysWlanObject)

## SysWlanObject 成员列表

### SysWlanObject.close()

关闭对象�?
关闭对象后不能再使用其他函数�?
此函数在对象析构时会自动调用，可重复调用

### SysWlanObject.eachProfile()

```aardio aardio
for name,guid,description,flags,access,xmlProfile in SysWlanObject.eachProfile(){
    /*遍历无线网络配置�?xmlProfile 为包含网络配置的 string.xml 对象�?name 为配置名
guid 为网�?GUID,win.guid 对象
description为网卡描�?其他参数请参考源�?/
}

[返回对象:stringXmlObject](#stringXmlObject)

```

### SysWlanObject.getInterfaces()

获取所有无线网卡，返回网卡信息数组�?
数组成员为包含网�?guid,description,state 等字段的结构体对象�?
细节请参考源码与相关 API 文档

### SysWlanObject.getProfileNames()

获取所有无线网络配置名，返回无线配置信息数组�?
数组成员为包含网�?name,flags,interfaceGuid,description 等字段的结构体对象�?
细节请参考源码与相关 API 文档

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/wlan.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/wlan.md')

