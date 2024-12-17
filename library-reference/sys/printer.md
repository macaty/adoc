[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.printer 库模块帮助文�?
## sys 成员列表

### sys.printer()

[返回对象:sysprinterObject](#sysprinterObject)

### sys.printer(printerName,printerDefaults)

打开打印机设�?
printerName指定打印机名�?省略打开默认打印�?
printerDefaults可省�?
## sys.printer 成员列表

### sys.printer.default()

返回默认打印机名�?
### sys.printer.device()

[返回对象:sysprinterdcObject](#sysprinterdcObject)

### sys.printer.device(hdc)

创建绘图设备对象

如果不指定hdc,则自动获取默认打印机绘图设备句柄

如果参数@2为true,则负责释放参数@1指定的hdc

### sys.printer.each(flags)

```aardio aardio
for printerName,serverName,attributes in sys.printer.each(){
    /*遍历系统打印�?
printerName为打机机名称,
serverName为服务名,
attributes为_PRINTER_ATTRIBUTE_前缀常量*/
}

```

### sys.printer.setDefault(名称)

设置默认打印�?
## sysprinterObject 成员列表

### sysprinterObject.createDevice()

创建绘图设备对象,

可选在参数中使用任意个键值对重新指定DEVMODE部分字段的�?
[返回对象:sysprinterdcObject](#sysprinterdcObject)

### sysprinterObject.documentProperties()

获取或修改DEVMODE缓冲区指�?
可选在参数中使用任意个键值对重新指定DEVMODE部分字段的�?
### sysprinterObject.endDoc()

结束打印一个文�?
### sysprinterObject.endPage()

结束打印一个页�?
### sysprinterObject.start(回调函数,文档�?文档类型,输出文件)

```aardio aardio
sysprinterObject.start(
    function(){

    }
);

```

### sysprinterObject.startDoc(docName,dataType,outputFile)

开始打印文�?所有参数可�?
参数参考API函数StartPagePrinter的说�?
### sysprinterObject.startPage()

开始打印一个页�?
### sysprinterObject.write()

写入字符�?
### sysprinterObject.writePack()

写入一个或多个字节�?
## sysprinterdcObject 成员列表

### sysprinterdcObject.dpi()

返回DPI

### sysprinterdcObject.endDoc()

结束打印一个文�?
### sysprinterdcObject.endPage()

结束打印一个页�?
### sysprinterdcObject.rect()

返回一个表示绘图区块的 RECT 结构�?
[返回对象:rectObject](../global/_.html#rectObject)

### sysprinterdcObject.reset()

修改打印机设�?
参数应为 sys.printer.documentProperties 函数返回�?DEVMODE 指针

### sysprinterdcObject.size()

返回 2 个返回值，分别为绘图区块的宽，高�?
### sysprinterdcObject.start(回调函数,文档�?文档类型,输出文件,类型)

```aardio aardio
sysprinterdcObject.start(
    function(hdcPrinter,rc){
        ::Gdi32.TextOut(hdcPrinter,20,20,"测试打印",4); /*回调参数 hdcPrinter 为绘图设备上下文句柄（hdc�?
rc 为绘图区块（ ::RECT 结构体）�?/
    }
);

```

### sysprinterdcObject.startDoc(docName,dataType,output,fwType)

开始打印文�?所有参数可�?
参数参�?API 函数 StartPage 的说�?
### sysprinterdcObject.startPage()

开始打印一个页�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/printer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/printer.md')

