[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.udp.xgimiClient 库模块帮助文�?
## wsock.udp.xgimiClient 成员列表

### wsock.udp.xgimiClient.enumDevice(proc)

```aardio aardio
wsock.udp.xgimiClient.enumDevice(
    function(deviceIp,friendlyName){

    }
)

```

## wsock.udp 成员列表

### wsock.udp.xgimiClient()

[返回对象:wsockUdpXgimiClientObject](#wsockUdpXgimiClientObject)

### wsock.udp.xgimiClient(deviceIp)

创建极米客户�?
## wsockUdpXgimiClientObject 成员列表

### wsockUdpXgimiClientObject.clearMemory()

清理内存

### wsockUdpXgimiClientObject.close()

关闭客户端对�?
### wsockUdpXgimiClientObject.controlCmd(cmd,delayTime)

发�?controlCmd 消息

可选用 @delayTime 参数指定执行后等待时间，单位毫秒

### wsockUdpXgimiClientObject.delayedShutdown(time)

延迟关机,参数�?
0=>取消�?=>15分钟�?=>30分钟�?=>60分钟�?=>120分钟

### wsockUdpXgimiClientObject.mute()

切换静音

### wsockUdpXgimiClientObject.openApp(app)

打开 APP

### wsockUdpXgimiClientObject.pressBack(repeat)

按后退�?
可选指定重复次�?
### wsockUdpXgimiClientObject.pressDown(repeat)

按下方向�?
可选指定重复次�?
### wsockUdpXgimiClientObject.pressHome()

按主页键

### wsockUdpXgimiClientObject.pressLeft(repeat)

按左方向�?
可选指定重复次�?
### wsockUdpXgimiClientObject.pressMenu()

按菜单键

### wsockUdpXgimiClientObject.pressOk(delayTime)

按确定键

可选用 @delayTime 参数指定执行后等待时间，单位毫秒

### wsockUdpXgimiClientObject.pressPower()

按电源键

### wsockUdpXgimiClientObject.pressRight(repeat)

按右方向�?
可选指定重复次�?
### wsockUdpXgimiClientObject.pressUp(repeat)

按上方向�?
可选指定重复次�?
### wsockUdpXgimiClientObject.pressVolumeDown(repeat)

按降低音量键

可选指定重复次�?
### wsockUdpXgimiClientObject.pressVolumeUp(repeat)

按增加音量键

可选指定重复次�?
### wsockUdpXgimiClientObject.printScreen()

截屏

### wsockUdpXgimiClientObject.reboot()

重启

### wsockUdpXgimiClientObject.search(data,delayTime)

语音搜索，参数指定要搜索的文�?
可选用 @delayTime 参数指定执行后等待时间，单位毫秒

### wsockUdpXgimiClientObject.sendKey(keyId,repeat,delayTime)

发送按�?
可选用 @repeat 参数指定重复次数

可选用 @delayTime 参数指定执行后等待时间，单位毫秒

### wsockUdpXgimiClientObject.sendMessage(delayTime)

发送消�?参数可以�?JSON 或表对象

可选用 @delayTime 参数指定执行后等待时间，单位毫秒

### wsockUdpXgimiClientObject.setting()

打开设置

### wsockUdpXgimiClientObject.shutdown()

直接关机

### wsockUdpXgimiClientObject.turnOfScreen()

关闭屏幕

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/wsock/udp/xgimiClient.md)

