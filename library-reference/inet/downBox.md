[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.downBox 库模块帮助文�?
## inet 成员列表

### inet.downBox

下载对话�?
### inet.downBox()

创建一个下载对话框

[返回对象:inetDownBoxObject](downBox.html#inetDownBoxObject)

### inet.downBox(父窗�?"标题",下载成功关闭超时)

所有参数可�?
参数@3可选指定下载成功自动关闭对话框的超时�?单位毫秒

## inetDownBoxObject 成员列表

### inetDownBoxObject.bufferSize

缓冲区大�?
不指定则默认�?28KB

### inetDownBoxObject.changeInterval(请输入ID,1000)

重新设定定时器的延时时间

### inetDownBoxObject.clearInterval(请输入ID)

删除定时�?
### inetDownBoxObject.complete

是否下载完成

### inetDownBoxObject.contentLength

文件长度

如果文件长度为零,并且modified属性为false,表示不需要重新下�?
### inetDownBoxObject.cookies

自定义HTTP请求头中的请求cookie

### inetDownBoxObject.download

弹出下载对话框并开始下载文�?
### inetDownBoxObject.download(URL,存储路径,配置文件,userAgent,proxy,... )

下载文件

参数@1指定下载网址,允许传入一个动态返�?url 的线程函�?
参数@2可以指定目录或文件路�?目录必须以反斜杠结尾,

其他参数可省�?
下载成功返回存储文路�?
userAgent,proxy等可选参数用于创建http对象,参考inet.http构造函数说�?
### inetDownBoxObject.endProc

```aardio aardio
inetDownBoxObject.endProc = function(savePath,fileSize,unmodified){
    /*下载成功触发此函数�?savePath 为下载文件路径�?fileSize 为文件大小，
文件未变更则 unmodified �?true*/
    if(!unmodified)
        owner.endModal();
}

```

### inetDownBoxObject.getPos()

返回相对坐标,�?�?
### inetDownBoxObject.headers

指定下载时的请求HTTP�?
### inetDownBoxObject.labInfo

显示信息

[返回对象:staticObject](../win/ui/ctrl/static.html#staticObject)

### inetDownBoxObject.labProgress

显示进度信息

[返回对象:staticObject](../win/ui/ctrl/static.html#staticObject)

### inetDownBoxObject.modified

文件在上次下载以后是否修改过

### inetDownBoxObject.modifyStyle(remove,add,swpFlags)

修改窗口样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### inetDownBoxObject.modifyStyleEx(remove,add,swpFlags)

修改窗口扩展样式,所有参数都是可选参�?

@remove 用数值指定要移除的样�?可使�?_WS\_EX_ 前缀的常�?
@add 用数值指定要添加的样�?可使�?_WS\_EX_ 前缀的常�?
@swpFlags 可选用数值指定调整窗口选项,可使�?_SWP_ 前缀的常�?
如果指定�?@swpFlag ,则使用该参数调用::SetWindowPos

细节请参�?win.modifyStyle 函数源码

### inetDownBoxObject.progress

进度�?
[返回对象:plusObject](#plusObject)

### inetDownBoxObject.referer

指定下载时的引用�?
### inetDownBoxObject.removeResumeFile()

移除断点续传配置文件

### inetDownBoxObject.savePath

下载成功后的文件存储路径

### inetDownBoxObject.setInterval(回调函数,延时毫秒�?...)

```aardio aardio
inetDownBoxObject.setInterval(回调函数,延时毫秒�?...setInterval(
    function(){
        /*参数@1指定执行函数,参数@2指定执行间隔�?可选指定一个或多个回调参数，不指定回调参数则默认为:
 hwnd,message,timerId,tick,

如果在定时器中执行了win.delay等继续消息循环的代码�?在定时器退出前不会再触发同一定时器（重入）�?
定时器回调函数返回数值可修改时间间隔,
返回false取消该定时器*/
    },1000
)

```

### inetDownBoxObject.setPos(x,y,�?�?插入位置,参数)

调整窗口位置或排�?
所有参数可�?
### inetDownBoxObject.setTimeout(函数�?延时,其他参数)

延时执行函数

### inetDownBoxObject.statusCode

HTTP状态码

### inetDownBoxObject.test(URL,存储路径,配置文件,userAgent,proxy,... )

检测是否已下载最新文�?
参数@1指定下载网址

参数@2可以指定目录或文件路�?目录必须以反斜杠结尾,

已下载文件未变更返回true

需要下载或续传返回false,下载错误返回null

userAgent,proxy等可选参数用于创建http对象,参考inet.http构造函数说�?
### inetDownBoxObject.text

对话框标�?
### inetDownBoxObject.userAgent

指定下载时的请求User Agent

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/downBox.md)

