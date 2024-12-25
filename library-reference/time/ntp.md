[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# time.ntp 库模块帮助文�?
## time.ntp 成员列表

### time.ntp.getData("ntp服务�?,端口,超时)

除参数@1之外所有参数可�?
参数@1也可以用一个数组指定多个服务器,

因为网络的不稳定�?该函数可能失败返回null

### time.ntp.getData()

[返回对象:wsockNtpDataObject](#wsockNtpDataObject)

### time.ntp.updateSystemTime()

使用NTP服务器获取的时间校正系统时间,

可选在参数中使用time对象指定要设置的时间

需要以管理员权限启动当前进�?

[返回对象:timeObject](_.html#timeObject)

## wsockNtpDataObject 成员列表

### wsockNtpDataObject.delayMilliseconds

服务端到客户端延时�?
毫秒

### wsockNtpDataObject.header

报文�?
### wsockNtpDataObject.poll

轮询时间，即发送报文的最小间隔时�?
### wsockNtpDataObject.precision

时钟的精�?
### wsockNtpDataObject.rootDelay

到主参考时钟的总往返延迟时�?
### wsockNtpDataObject.rootDispersion

本地时钟相对于主参考时钟的最大误�?
### wsockNtpDataObject.stratum

时钟的层数，定义了时钟的准确度。层数为1的时钟准确度最高，�?�?6依次递减

### wsockNtpDataObject.time

报文返回后计算出的当前时�?
[返回对象:timeObject](_.html#timeObject)

## wsockNtpDataObject.originateTimestamp 成员列表

客户端报文发送时�?
### wsockNtpDataObject.originateTimestamp.time

[返回对象:timeObject](_.html#timeObject)

## wsockNtpDataObject.receiveTimestamp 成员列表

NTP服务器接收报文时�?
### wsockNtpDataObject.receiveTimestamp.time

[返回对象:timeObject](_.html#timeObject)

## wsockNtpDataObject.referenceIdentifier 成员列表

参考时钟源的标�?
### wsockNtpDataObject.referenceIdentifier.time

[返回对象:timeObject](_.html#timeObject)

## wsockNtpDataObject.referenceTimestamp 成员列表

最后一次更新的时间

### wsockNtpDataObject.referenceTimestamp.time

[返回对象:timeObject](_.html#timeObject)

## wsockNtpDataObject.transmitTimestamp 成员列表

NTP服务器报文发送时�?
### wsockNtpDataObject.transmitTimestamp.time

[返回对象:timeObject](_.html#timeObject)

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/time/ntp.md)

