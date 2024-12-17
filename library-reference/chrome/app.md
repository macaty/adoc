[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# chrome.app 库模块帮助文�?
## chrome 成员列表

### chrome.app()

[返回对象:processchromeappObject](#processchromeappObject)

### chrome.app(父窗�?chrome启动程序路径)

调用系统已安装的chrome创建应用程序

所有参数可选，参数@2也可以指定CEF3启动程序cefclient.exe的路�?
使用CEF3支持在参数@1指定父窗口并嵌入浏览器到该窗�?

原版Chrome嵌入父窗口会出现兼容性问�?

[返回对象:processchromeappObject](#processchromeappObject)

## chrome.app 成员列表

调用系统已安装的 Chrome 创建应用程序�?
支持 Chrome �?Edge（Chromium ）、Supermium 等浏览器�?
如果没有找到可用的浏览器会下载安�?Microsoft Edge (Chromium)�?
Win7 则自动安�?Chrome 109，XP 自动安装 Chrome 49

### chrome.app.path

自定义Chrome.exe位置,

支持Chrome,兼容Chrome启动参数的Chrome内核浏览�?

也可以指定CEF3启动程序cefclient.exe

## processchromeappObject 成员列表

### processchromeappObject.\_form

创建chrome.app时指定的父窗�?
[返回对象:staticObject](../win/ui/ctrl/static.html#staticObject)

### processchromeappObject.accessControlAllowOrigin

允许写入 Access-Control-Allow-Headers 响应头的站点地址�?
此属性必须为 null、字符串，或者指定为一个表对象,

表的键为允许跨域调用的站点地址,值必须为 true

站点地址应使�?https://host 格式，且结尾不要有斜杠，

新的浏览器已经禁止在�?HTTPS 协议下调用本机地址�?
而老版浏览器则反之

### processchromeappObject.accessControlRequestPrivateNetwork

自定�?Access-Control-Request-Private-Network 响应头的值，

默认�?"true"，可改为 null

### processchromeappObject.addArguments()

添加一个或多个Chrome启动参数,

参数也可以是一个包含多个启动参数的数组

注意参数中不必要使用引号,多个参数应分开写不要拼接成一个参�?
每个启动参数都是使用两个横杠开始的字符�?
[chrome启动参数大全](javascript:if(confirm('https://peter.sh/experiments/chromium-command-line-switches/  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://peter.sh/experiments/chromium-command-line-switches/')

### processchromeappObject.callback(name,callback)

```aardio aardio
processchromeappObject.callback("/*要接收返回值的JS函数�?
回调叁数$为RPC客户端套接字句柄
成功result为返回�?失败err为错误信�?/",function($,result,err){

})

```

### processchromeappObject.center

居中窗口,并调整以保证显示在可见范围内,

如果要调用此函数,建议在调�?start 函数前调�?

只有浏览器显示为独立窗口时才支持此函�?
### processchromeappObject.center(目标窗口句柄)

居中窗口,并调整以保证显示在可见范围内,

如果要调用此函数,建议在调�?start 函数前调�?

目标窗口句柄如果为空则取父窗口或所有者窗�?�?表示桌面

### processchromeappObject.chromePath

chrome启动exe文件路径

### processchromeappObject.chromeProcessId

chrome进程ID

注意chrome可能会使用一个进程启动多个独立的应用

### processchromeappObject.chromeThreadId

chrome启动线程ID

### processchromeappObject.close()

关闭chrome窗口

### processchromeappObject.doScript($,js,...)

在chrome中执行javascript代码,忽略返回�?

在js参数后可选指定多个字符串格式化参数用于调用string.form格式化代�?

参数@1指定客户端套接字句柄,

RPC服务端远程回调函数名首字符为$�?

第一个回�?参数即为当前客户端套接字句柄,

除非熟悉 getActiveSocket 函数导致的潜在问�?请不要省�?参数

### processchromeappObject.external

```aardio aardio
processchromeappObject.external = {
    /*可以在这里指定允许chrome访问的对象和函数
在chrome里引用虚拟的"/aardio.js"导入aardio对象即可访问这里的成员函�?
必须在调用start函数以前设置此对象才能生�?/
}

```

### processchromeappObject.favicon

指定窗口图标路径

默认�?res/favicon.ico

### processchromeappObject.getActiveSocket()

获取RPC服务端当前活动套接字句柄

,任何触发消息处理、异步套接字处理程序的代码都有可能改变这个函数的返回�?
任何时候都不推荐使用此函数

更好的替代方案是在RPC函数名前添加$字符,用于通知aardio在回调参数中添加$参数

回调$参数可以稳定可靠的获取当前套接字

### processchromeappObject.getUrl("/")

参数指定资源文件路径,

转换并返回为可以通过内嵌 HTTP 服务端访问的网址

如果使用 start 函数启动了单页应用，且启动文件名�?"index.html" �?"index.aardio"�?
chrome.app 会自动将启动路径的上级目录设�?http.documentBase�?
此时 getUrl 的参数应当以 http.documentBase 为根目录

### processchromeappObject.http

aardio创建的HTTP服务�?
[返回对象:asynHttpServerObject](../wsock/tcp/asynHttpServer.html#asynHttpServerObject)

### processchromeappObject.httpHandler

```aardio aardio
processchromeappObject.httpHandler["/test.js" ] = function(response,request){
    /*自定义HTTP处理程序
键为请求的路�?值为处理函数或者HTML代码*/
}

```

### processchromeappObject.hwndChrome

chrome窗口句柄

如果在wine环境下运行，此窗口句柄为空�?依赖此句柄的部分chrome窗口操作函数将无�?
### processchromeappObject.indexReady

```aardio aardio
processchromeappObject.indexReady(
    function($){
        /*如果加载首页已完�?
并且页面上的DOM内容、aardio模块都已准备就绪,
将立即执行在此注册的回调函数,
可重复添加回调，并保证按添加的前后顺序调用且仅调用一�?参数 $ 为触发此事件的网页RPC客户端套接字句柄*/
    }
)

```

### processchromeappObject.msgbox("字符串参�?)

弹出对话�?
参数@1指定显示的数�?如果是表对象先序列化为文�?

其他对象调用tostring转换为文�?
此函数调用win.msgbox,但设定父窗口为当前chrome窗体

### processchromeappObject.msgbox("字符串参�?,"标题")

弹出对话�?
参数@1指定显示的数�?如果是表对象先序列化为文�?

其他对象调用tostring转换为文�?
此函数调用win.msgbox,但设定父窗口为当前chrome窗体

### processchromeappObject.msgboxErr("字符串参�?)

弹出错误对话�?
参数@1指定显示的数�?如果是表对象先序列化为文�?

其他对象调用tostring转换为文�?
此函数调用win.msgbox,但设定父窗口为当前chrome窗体

### processchromeappObject.msgboxErr("字符串参�?,"标题")

弹出错误对话�?
参数@1指定显示的数�?如果是表对象先序列化为文�?

其他对象调用tostring转换为文�?
此函数调用win.msgbox,但设定父窗口为当前chrome窗体

### processchromeappObject.msgboxTest("字符串参�?)

弹出询问对话�?
参数@1指定显示的数�?如果是表对象先序列化为文�?

其他对象调用tostring转换为文�?
此函数调用win.msgbox,但设定父窗口为当前chrome窗体

### processchromeappObject.notify($,"method",...)

调用指定chrome函数,但不需要客户端回调反馈,

参数@1指定客户端套接字句柄,

RPC服务端远程回调函数名首字符为$�?

第一个回�?参数即为当前客户端套接字句柄,

除非熟悉getActiveSocket函数导致的潜在问�?请不要省�?参数

### processchromeappObject.onClose

```aardio aardio
processchromeappObject.onClose = function($hSocket,err){
    /*一个网页窗口断开连接触发此事�?/
}

```

### processchromeappObject.onError

```aardio aardio
processchromeappObject.onError = function($hSocket,err){
    errput(err,"chrome/rpc error");/*自定义RPC错误处理*/
}

```

### processchromeappObject.onIndexReady

```aardio aardio
processchromeappObject.onIndexReady = function(){
    /*主窗口首次加载完成startEnviron.indexUrl指定的首�?
并且页面上的DOM内容、aardio模块都已准备就绪*/
}

```

### processchromeappObject.onQuit

```aardio aardio
processchromeappObject.onQuit = function(){
    ..win.quitMessage();/*Chrome关闭网页客户端触发此代码
此事件触发以后hwndChrome会变为空�?/
}

```

### processchromeappObject.onUrlReady

```aardio aardio
processchromeappObject.onUrlReady = function(hSocket,url){
    /*页面加载完成并且页面上的DOM内容、aardio模块都已准备就绪*/
}

```

### processchromeappObject.publish(method,...)

主动向所有客户端发送通知

method指定网页客户端方法名,

可添加任意个调用参数

### processchromeappObject.remoteDebuggingPort

指定远程调试端口

如果指定�?，则自动分配1025以后的空闲端�?
此属性启动后更新为实际开始的调试端口�?
### processchromeappObject.rpc

aardio创建的JSON-RPC服务�?
[返回对象:websocketjsonserverObject](#websocketjsonserverObject)

### processchromeappObject.serverIp

指定嵌入服务器的监听IP

默认值为 "127.0.0.1",仅限本机可以访问

如果希望外网可以访问,可以赋值为null即可

在调用start函数以前指定此属性才有效

### processchromeappObject.serverPort

指定嵌入服务器的监听端口

建议保持默认值null

不指定端口可以随机分配空闲端口，不会出现端口冲突的问�?
在调用start函数以前指定此属性才有效

### processchromeappObject.setPos

调整窗口位置或排序，所有参数可选�?
如果要调用此函数，建议在调用 start 函数前调用�?
只有浏览器显示为独立窗口时才支持此函�?
### processchromeappObject.setPos(x坐标,y坐标,�?�?插入位置,选项)

调整窗口位置或排序，所有参数可选�?
此函数将根据当前 DPI 缩放设置自动缩放参数�?
同时指定 x，y 坐标则移动位置�?
同时指定宽高则改变大小�?
指定插入位置<句柄或\_HWND前缀常量>则调整Z序�?
选项不用指定，可参考此函数源码了解细节

### processchromeappObject.start(url)

启动chrome应用

参数@1可以指定资源目录下的aardio文件,

aardio 会自动使用嵌入HTTP服务器调用该文件�?
自动支持嵌入资源路径�?SPA 单页应用�?
如果同时文件名为 index.html �?"index.aardio"�?
则上级目录设�?http.documentBase 根目录，

后续请求网址应当�?"/" 代替 http.documentBase 根目�?
### processchromeappObject.start(url,devPort,timeout)

启动 Chrome 应用

参数@1可以指定资源目录下的 aardio 文件,

在开发环境中可选用devPort指定前端项目调试服务器端�?
自动支持嵌入资源路径�?SPA 单页应用�?
如果同时文件名为 index.html，则上级目录设为根目录，且路径转换为 "/index.html"

### processchromeappObject.start(url,laucher)

启动 Chrome 应用

参数@1可以指定资源目录下的 aardio 文件,

可选在参数@2中指定一个函数对象用于自定义启动Chrome的代�?

此启动函数唯一的回调参数是一个包含Chrome启动参数的数�?
自定义启动函数成功应返回true

### processchromeappObject.survey(method,...)

发起调查任务,

调用所有网页客户端的同名函�?

method指定客户端方法名,

可添加任意个调用参数

请使用callback函数指定调查结束后客户端回调的函�?
### processchromeappObject.userDataDir

设置用户数据目录,

使用 fsys.environment自动转换%LocalAppData%等路径环境变�?
远程调试以及全屏功能，都要求使用同一用户数据目录时只有一个正在运行的chrome进程

### processchromeappObject.ws

aardio创建的WebSocket服务�?
[返回对象:websocketserverObject](#websocketserverObject)

### processchromeappObject.xcall($,"method",...)

调用chrome函数,

参数@1指定客户端套接字句柄,

RPC服务端远程回调函数名首字符为$�?第一个回�?参数即为当前客户端套接字句柄,

除非熟悉getActiveSocket函数导致的潜在问�?请不要省�?参数

在chrome的js代码使用 aardio.on("method")

添加允许aardio调用的js回调函数.

可选使用callback函数指定一个同名回调函数按收本次调用chrome的返回�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/chrome/app.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/chrome/app.md')

