[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.tcp.simpleHttpServer 库模块帮助文�?
## wsock.tcp.simpleHttpServer 成员列表

HTTP服务�?
支持文件上传,下载,下载支持断点续传

支持多线程处理请�?
### wsock.tcp.simpleHttpServer.defalutDocument

默认文档，默认为"main.aardio",

如果访问硬盘上存在的目录,request.path 尾部不加斜杠会自动跳转到以斜杆结束的路径

如果访问嵌入资源目录,只有 request.path 以斜杆才会访问默认文�?

对于访问嵌入资源文件,建议指定完整的文件路�?

默认文档主要是用于硬盘上的网�?
### wsock.tcp.simpleHttpServer.documentBase

网站根目�?

不会修改应用程序根目�?支持硬盘目录与资源目�?

这个属性应当设置为应用程序根目录下的相对路�?

例如 "/res/web/"

注意�?request.path 前面包含 documentBase 目录�?
�?request.pathInfo 忽略 documentBase 目录

### wsock.tcp.simpleHttpServer.documentRoot

网站应用程序根目�?默认�?/",

只能设置为硬盘上实际存在的目�?

改变此目�?会同时改�?
服务端代码中的应用程序根目录以及用户库目�?

如果只是相将所有请求路径转向某个目�?应当改用 documentBase 属�?
如果网站在嵌入资源目录中,应当改用 documentBase 属�?
### wsock.tcp.simpleHttpServer.mainThread()

[返回对象:HttpSimpleServerMainObject](#HttpSimpleServerMainObject)

### wsock.tcp.simpleHttpServer.mainThread(app)

```aardio aardio
wsock.tcp.simpleHttpServer.mainThread(
    function(response,request,session){
         response.loadcode( request.path /*可省�?可增加多个模板参�?
在被调用文件的函数外部可使用owner参数获取首个模板参数,
也可以使�?..获取多个模板参数*/ );
    }
);

```

### wsock.tcp.simpleHttpServer.startSpaUrl

返回 SPA 单页应用首页网址

### wsock.tcp.simpleHttpServer.startSpaUrl(indexHtmlPath,documentBase,app)

参数指定 SPA 单页应用首页路径�?
404错误页也会自动设置到该路径，

返回首页网址

可选用参数 @documentBase 指定根目�?
以避免网页不支持非根目录路径�?
可选用 @app 参数指定处理 HTTP 请求的线程函数，

该线程函数有 response,request,session 等三个回调参�?
### wsock.tcp.simpleHttpServer.startUrl

查找可用端口创建 HTTP 服务器线程，返回返回完整 URL

此服务端限制使用本机IP 127.0.0.1 访问,并随机分配端口不会出现端口冲�?
如果HTTP服务器已启动则直接返回URL而不是重复启动服务器,

注意当前线程结束�?此服务器线程会自动退�?
### wsock.tcp.simpleHttpServer.startUrl(path,documentRoot,app)

查找可用端口创建 HTTP 服务器线程，返回返回完整 URL

如果 HTTP 服务器已启动则直接返�?URL 而不是重复启动服务器�?
省略参数返回首页URL,尾部不包含斜杠�?
可选用 @path 参数指定请求目标文件的相对路径�?
可选使用参�?@documentRoot 指定网站根目�?默认�?/"�?
documentRoot 只能设为硬盘实际存在的目录，并会改变用户库与应用根目录，

如只想改变网页根目录请设�?wsock.tcp.simpleHttpServer.documentBase�?
可选用 @app 参数指定处理 HTTP 请求的线程函�?

该线程函数有 response,request,session 等三个回调参数�?
也可以用参数@1 指定 @app 参数�?
### wsock.tcp.simpleHttpServer.stopUrl()

退出startUrl函数创建的HTTP服务器线�?
## HttpSimpleServerMainObject 成员列表

### HttpSimpleServerMainObject.customErrors

```aardio aardio
HttpSimpleServerMainObject.customErrors = {
    [404] = function(response){
        response.status = "404 Not Found";
        response.write("404 Not Found"); /*自定义错误页*/
    }
}

```

### HttpSimpleServerMainObject.defalutDocument

默认文档，默认为"main.aardio",

如果访问硬盘上存在的目录,request.path 尾部不加斜杠会自动跳转到以斜杆结束的路径

如果访问嵌入资源目录,只有 request.path 以斜杆才会访问默认文�?

对于访问嵌入资源文件,建议指定完整的文件路�?

默认文档主要是用于硬盘上的网�?
### HttpSimpleServerMainObject.documentBase

网站根目�?

不会修改应用程序根目�?支持硬盘目录与资源目�?

这个属性应当设置为应用程序根目录下的相对路�?

例如 "/res/web/",

注意�?request.path 前面包含 documentBase 目录�?
�?request.pathInfo 忽略 documentBase 目录

### HttpSimpleServerMainObject.documentRoot

网站应用程序根目�?默认�?/",

只能设置为硬盘上实际存在的目�?

改变此目�?会同时改�?
服务端代码中的应用程序根目录以及用户库目�?

如果只是相将所有请求路径转向某个目�?应当改用 documentBase 属�?
如果网站在嵌入资源目录中,应当改用 documentBase 属�?
### HttpSimpleServerMainObject.getLocalIp()

返回服务端IP,端口

### HttpSimpleServerMainObject.getUrl()

返回HTTP服务端访问网址,可选指定目录或文件路径

注意参数第一个字符不需要指定斜�?
如果参数@2为true，IP "0.0.0.0"替换为合适的内网IP而不是localhost

如果服务器启动失败不返回任何�?
### HttpSimpleServerMainObject.onThreadCreated()

```aardio aardio
HttpSimpleServerMainObject.onThreadCreated = function(documentRoot,urlRoot){
    /*一个HTTP服务监听线程准备就绪时触发此事件*/
}

```

### HttpSimpleServerMainObject.serverId

当前服务端唯一ID，字符串,

每次调用start函数都会改变这个属性的�?
### HttpSimpleServerMainObject.start(IP,端口,请求队列大小)

启动HTTP服务�?
### HttpSimpleServerMainObject.startPort

设置服务器端�?默认自动分配空闲端口

### HttpSimpleServerMainObject.startSpaUrl

返回 SPA 单页应用首页网址

### HttpSimpleServerMainObject.startSpaUrl(indexHtmlPath,documentBase)

参数指定 SPA 单页应用首页路径�?
404错误页也会自动设置到该路径，

返回首页网址

可选用参数 @documentBase 指定根目录以避免网页不支持非根目录路�?
### HttpSimpleServerMainObject.stop()

停止HTTP服务�?
### HttpSimpleServerMainObject.threadGlobal

```aardio aardio
HttpSimpleServerMainObject.threadGlobal = {
    /*在onThreadCreated事件触发�?添加HTTP服务监听线程的全局变量*/
}

```

### HttpSimpleServerMainObject.threadNum

设置服务器线程数，默认为2个线�?
## HttpSimpleServerObject 成员列表

### HttpSimpleServerObject.\_serverAddress

服务端监听地址

[返回对象:sockaddrInObject](#sockaddrInObject)

### HttpSimpleServerObject.beforeClose()

```aardio aardio
HttpSimpleServerObject.beforeClose = function(){
    /*服务器关闭前调用此函�?/
}

```

### HttpSimpleServerObject.close()

关闭 HTTP 服务�?
### HttpSimpleServerObject.customErrors\[404\]

```aardio aardio
HttpSimpleServerObject.customErrors[404] = function(response){
    response.status = "404 Not Found";
    response.write("404 Not Found"); /*自定义错误页处理函数�?注意这是线程函数，应遵守多线程规则，
也可以直接指定错误页路径*/
}

```

### HttpSimpleServerObject.defalutDocument

默认文档，默认为"main.aardio",

在启动服务端之前设置才会生效,

如果访问硬盘上存在的目录,request.path 尾部不加斜杠会自动跳转到以斜杆结束的路径

如果访问嵌入资源目录,只有 request.path 以斜杆才会访问默认文�?

对于访问嵌入资源文件,建议指定完整的文件路�?

默认文档主要是用于硬盘上的网�?
### HttpSimpleServerObject.documentBase

网站根目�?

在启动服务端之前设置才会生效,

不会修改应用程序根目�?支持硬盘目录与资源目�?

这个属性应当设置为应用程序根目录下的相对路�?

例如 "/res/web/"

注意�?request.path 前面包含 documentBase 目录�?
�?request.pathInfo 忽略 documentBase 目录

### HttpSimpleServerObject.documentRoot

网站应用程序根目�?默认�?/",

在启动服务端之前设置才会生效,

只能设置为硬盘上实际存在的目�?

改变此目�?会同时改�?
服务端代码中的应用程序根目录以及用户库目�?

如果只是相将所有请求路径转向某个目�?应当改用 documentBase 属�?
如果网站在嵌入资源目录中,应当改用 documentBase 属�?
### HttpSimpleServerObject.getLocalIp()

返回当前绑定的IP,端口�?
### HttpSimpleServerObject.getUrl()

返回首页URL

如果参数@1为true，IP "0.0.0.0"替换为上网卡IP而不是localhost

### HttpSimpleServerObject.listen(请求队列大小)

监听构造函数绑定的 IP 端口，成功返�?true �?
已自动调用此函数�?
### HttpSimpleServerObject.onThreadCreated()

```aardio aardio
HttpSimpleServerObject.onThreadCreated = function(documentRoot,urlRoot){
    /*一个HTTP服务监听线程准备就绪时触发此事件*/
}

```

### HttpSimpleServerObject.run( httpProc )

```aardio aardio
HttpSimpleServerObject.run(
    function(response,request,session){
         response.loadcode( request.path /*可省�?可增加多个模板参�?
在被调用文件的函数外部可使用owner参数获取首个模板参数,
也可以使�?..获取多个模板参数*/ );
    }
);

```

### HttpSimpleServerObject.threadGlobal

```aardio aardio
HttpSimpleServerObject.threadGlobal = {
    /*在onThreadCreated事件触发�?添加HTTP服务监听线程的全局变量*/
}

```

### HttpSimpleServerObject.threadNum

设置服务器线程数，默认为2个线�?
## wsock.tcp 成员列表

### wsock.tcp.simpleHttpServer()

[返回对象:HttpSimpleServerObject](#HttpSimpleServerObject)

### wsock.tcp.simpleHttpServer(IP,端口,请求队列大小)

创建HTTP服务�?所有参数可�?

如果不写IP，则默认设为"0.0.0.0"也即监听本机所有IP,访问此服务端也不限制IP

限制仅本机可以访问建议写127.0.0.1

端口�?或省略则自动选择未用端口

注意0-1023为系统通用服务保留端口,

1024-49151为用户服务端�?其中大约%9已由IANA注册分配

49152-65535为私有或临时端口

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/simpleHttpServer.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/simpleHttpServer.md')

