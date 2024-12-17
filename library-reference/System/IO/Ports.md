[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# System.IO.Ports 库模块帮助文�?
## System.IO.Ports 成员列表

.NET System.IO.Ports 名字空间

Win7 �?.NET 2.0 开始自带此组件

### System.IO.Ports.?

.NET 名字空间、类、结构体的成员，

可访问成员名字空间、类、枚举、静态属性或字段�?
导入的类可用于构�?.NET 对象，传�?.NET 则自动转为该类的 Type 对象

[返回对象:dotNetNameSpaceObject](../../dotNet/appDomain.html#dotNetNameSpaceObject)

### System.IO.Ports.SerialPort()

[返回对象:systemIoSerialPortObject](#systemIoSerialPortObject)

### System.IO.Ports.SerialPort(portName,baudRate)

打开串口�?
可选用 @portName 指定端口名，例如 "COM1"�?
可选用 @baudRate 参数指定波特�?
### System.IO.Ports.assembly

导入�?.NET 名字空间的程序集对象�?
[返回对象:dotNetCrlAssemblyObject](#dotNetCrlAssemblyObject)

## System.IO.Ports.SerialPort 成员列表

串口设备

打开串口

### System.IO.Ports.SerialPort.GetPortNames ()

返回包含所有串口名的字符串数组

## systemIoSerialPortObject 成员列表

### systemIoSerialPortObject.BaseStream

获取底层 System.IO.Stream 对象�?
### systemIoSerialPortObject.BaudRate

获取或设置串行波特率�?
### systemIoSerialPortObject.BreakState

获取或设置中断信号状态�?
### systemIoSerialPortObject.BytesToRead

获取接收缓冲区中的数据字节数�?
### systemIoSerialPortObject.BytesToWrite

获取发送缓冲区中的数据字节数�?
### systemIoSerialPortObject.CDHolding

获取端口�?Carrier Detect 线路状态�?
### systemIoSerialPortObject.CanRaiseEvents

获取一个值，指示组件是否能够触发事件�?
### systemIoSerialPortObject.Container

获取包含该组件的 IContainer�?
### systemIoSerialPortObject.CtsHolding

获取 Clear-to-Send 线路的状态�?
### systemIoSerialPortObject.DataBits

获取或设置每字节的标准数据位长度�?
### systemIoSerialPortObject.DataReceived

```aardio aardio
systemIoSerialPortObject.DataReceived = function(sender,e){
    try{
        var str = sender.ReadExisting();
        /*str 为串口接收的文本数据，字符串�?为避免收到乱码，Encoding 属性要正确设置文本编码�?或者改�?read 函数读取二进制的字节数组�?
这个回调函数如果抛出异常，程序会退出�?建议代码写在 try 语句中，�?catch 语句中获取错误信息�?
注意无论 .NET 是否多线程回调，
�?.NET 回调�?aardio 函数总会在原调用线程执行�?不需要考虑多线程规则与同步问题*/

    }
    catch(e){

    }
}

```

### systemIoSerialPortObject.DiscardNull

获取或设置一个值，指示在端口和接收缓冲区之间传输时是否忽略空字节�?
### systemIoSerialPortObject.DsrHolding

获取数据集准�?(DSR) 信号的状态�?
### systemIoSerialPortObject.DtrEnable

获取或设置一个值，在串行通信期间启用数据终端就绪 (DTR) 信号�?
### systemIoSerialPortObject.Encoding

获取或设置读写字符串值时使用的默认文本编码�?
可设�?System.Text.UTF8Encoding 等编码类的实例对象�?
默认值为 System.Text.ASCIIEncoding 对象�?
读写二进制字节数组与 Encoding 无关

### systemIoSerialPortObject.ErrorReceived

```aardio aardio
systemIoSerialPortObject.ErrorReceived = function(sender,e){
    var eventType = e.EventType;
    /*发生错误，eventType �?System.IO.Ports.SerialError 枚举 */
}

```

### systemIoSerialPortObject.Events

获取附加到此组件的事件处理程序列表�?
### systemIoSerialPortObject.Handshake

获取或设置使�?Handshake 值的串行端口数据传输的握手协议�?
### systemIoSerialPortObject.IsOpen

获取一个值，指示 SerialPort 对象的打开或关闭状态�?
### systemIoSerialPortObject.NewLine

获取或设置用于解�?ReadLine() �?WriteLine(String) 方法结束的值�?
### systemIoSerialPortObject.Open()

创建连接

### systemIoSerialPortObject.Parity

获取或设置奇偶校验协议�?
### systemIoSerialPortObject.ParityReplace

获取或设置在奇偶校验错误发生时替换数据流中的无效字节的字节�?
### systemIoSerialPortObject.PortName

获取或设置用于通信的端口，包括但不限于所有可用的 COM 端口�?
### systemIoSerialPortObject.Read(bytes,offset,count)

读取数据�?
@bytes �?buffer 对象或者字节码数组�?
@offset 指定为数据写入参数@1的索引偏移量�? 为自第一个字节开始写入�?
@count 指定自指定索引开始写入的字节�?
### systemIoSerialPortObject.ReadBufferSize

获取或设�?SerialPort 输入缓冲区的大小�?
### systemIoSerialPortObject.ReadByte()

同步读取一个字节，返回数�?
### systemIoSerialPortObject.ReadChar()

同步读取一个字符，返回数�?
### systemIoSerialPortObject.ReadExisting()

根据编码读取所有可用字节，返回字符�?
### systemIoSerialPortObject.ReadLine()

读取一行字符串

### systemIoSerialPortObject.ReadTimeout

获取或设置读取操作未完成时发生超时之前的毫秒数�?
### systemIoSerialPortObject.ReceivedBytesThreshold

获取或设置在数据接收到内部输入缓冲区之前，DataReceived 事件发生时的字节数�?
### systemIoSerialPortObject.RtsEnable

获取或设置一个值，指示在串行通信期间是否启用请求发�?(RTS) 信号�?
### systemIoSerialPortObject.Site

获取或设置组件的 ISite�?
### systemIoSerialPortObject.StopBits

获取或设置每字节的标准停止位数�?
### systemIoSerialPortObject.Write

发送数�?
### systemIoSerialPortObject.Write(bytes,offset,count)

发送数据�?
@bytes �?buffer 对象或者字节码数组�?
@offset 指定索引偏移量，0 为自第一个字节开始发送�?
@count 指定自指定索引开始发送的字节�?
### systemIoSerialPortObject.Write(str)

发送数据�?
@str 指定要发送的字符串�?
### systemIoSerialPortObject.WriteBufferSize

获取或设置串行端口输出缓冲区的大小�?
### systemIoSerialPortObject.WriteLine(str)

发送数据并添加换行�?
@str 指定要发送的字符串�?
### systemIoSerialPortObject.WriteTimeout

获取或设置写操作未完成时发生超时之前的毫秒数�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/System/IO/Ports.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/System/IO/Ports.md')

