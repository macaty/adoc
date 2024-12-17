[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 获取磁盘属�?
```aardio aardio
//获取磁盘属�?import console;
import sys.storage;

//获取所有磁盘分区（硬盘、U 盘），参�?@2 �?true 则仅获取 U 盘信�?var device = sys.storage.getDevices(true,/*true*/);

// 检测USB设备
for i,path in device {

    // 获取设备属�?    var properties = sys.storage.queryProperty(path)

    // 输出设备信息
    console.log("设备路径:", path)
    console.log("序列�?", properties.serialNumber)
    console.log("产品版本:", properties.productRevision)
    console.log("产品ID:", properties.productId)
    console.log("厂商ID:", properties.vendorId)
    console.log("设备类型:", properties.deviceType)
    console.log("设备类型修饰�?", properties.deviceTypeModifier)
    console.log("是否可移�?", properties.removableMedia)
    console.log("是否支持命令队列:", properties.commandQueueing)
    console.log("总线类型:", properties.busType)

    console.more(1);
}

console.pause(true)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Storage/storage.properties.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Storage/storage.properties.md')

