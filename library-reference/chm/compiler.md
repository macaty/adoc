[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# chm.compiler 库模块帮助文�?
## chm 成员列表

### chm.compiler("HHP文件路径")

创建可打开CHM工程文件

### chm.compiler()

[返回对象:chmCompilerObject](#chmCompilerObject)

## chmCompilerObject 成员列表

### chmCompilerObject.compile()

编译生成CHM文件

可选在参数中指定输出CHM文件路径

### chmCompilerObject.compiledFile

输出的CHM文件路径

### chmCompilerObject.contentsFile

目录文件

### chmCompilerObject.defaultFont

默认字体,默认�?"Tahoma,10,0"

### chmCompilerObject.defaultTopic

默认首页

### chmCompilerObject.defaultWindow

默认窗体名字

### chmCompilerObject.displayCompileProgress

是否显示进度,默认�?Yes"

### chmCompilerObject.fullTextSearch

是否全文搜索,默认�?"Yes"

### chmCompilerObject.hhpInfo

配置文件

[返回对象:iniObject](#iniObject)

### chmCompilerObject.indexFile

索引文件

### chmCompilerObject.language

LCID 语言代码

### chmCompilerObject.navigationPaneWidth

左侧导航栏宽�?默认�?220

### chmCompilerObject.navigationStyle

左侧导航栏样�?数�?

默认�?0x60420

### chmCompilerObject.onPrint

```aardio aardio
chmCompilerObject.onPrint = function( str ){
    io.print( str )/*参数为输出信�?
此回调函数返�?true 继续编译*/
    return true;
}

```

### chmCompilerObject.onProgress

```aardio aardio
chmCompilerObject.onProgress = function( str ){
    io.print( str )/*参数指示进度,
此回调函数返�?true 继续编译*/
    return true;
}

```

### chmCompilerObject.title

窗口标题

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/chm/compiler.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/chm/compiler.md')

