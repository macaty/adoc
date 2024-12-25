[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.http 库模块帮助文�?
入门教程

inet.http �?inet.whttp 用法与接口基本相同，一般可相互替代�?普通桌面客户端软件(非NT服务)请使�?inet.http（WinINet�?而不应该使用 inet.whttp（WinHTTP）�?基于 inet.http 而封装的 web.rest.client 可能在很多应用中都是更好的选择�?
inet.http 入门教程�?[https://www.aardio.com/zh-cn/doc/library-guide/std/inet/http.html](../../library-guide/std/inet/http.html)

inet.http 错误代码请参考库 inet.errorMessage

## inet 成员列表

### inet.http("UserAgent","代理服务�?,"绕过代理的主�?,连接选项)

创建 HTTP 客户端，所有参数可选�?
UserAgent 用于自定�?User-Agent 请求标头，用于服务器识别请求程序特征�?
代理服务器指定为""�?IE"使用系统代理设置（默认值）�?
HTTP 代理服务器请指定�?"代理服务器地址:端口" 格式�?
SOCKS 代理服务器请指定�?"socks=代理服务器地址:端口" 格式

└── [代理格式说明](../../library-guide/std/inet/proxy.html)

"绕过代理的主�? 用法参�?inet.setProxy 源码的示例，一般不需要指定�?
连接选项可用一个数值参数指定打开会话的选项，一般不需要指定�?
### inet.http("UserAgent",false)

禁用代理，UserAgent 为可选参�?
### inet.http()

[返回对象:inetHttpObject](#inetHttpObject)

## inet.http 成员列表

WinINet 支持�?
支持进程内多对象共享会话 cookie,支持持久�?cookie

�?web.form 浏览器控�?IE 浏览器共�?cookie 与代理设置�?
inet.http 错误代码请参考库 inet.errorMessage

创建HTTP会话对象,所有参数可选，

注意提前导入zlib库，readAll 函数才能支持 gzip 自动解压�?
### inet.http.get(url,headers,referer)

用于界面线程创建线程并获�?@url 指定网址的数�?

此函数等待下载完成但不会阻塞界面消息循环,

可选用 @headers 指定 HTTP �?

可选用 @referer 指定引用网址,

所有参数用法与 格式请参�?inet.http 对象�?get 函数相同

### inet.http.import(url)

自url指定的网址自远程导入单页扩展库

网址尾部的文件名必须�?扩展库名字空�? \+ ".aardio" 结尾

例如: inet.http.import(" [http://download.aardio.com/inetlib/remote.test.aardio"](http://download.aardio.com/inetlib/remote.test.aardio%22))

远程库代码里只能导入执行文件已经自带的库

### inet.http.isAlive("UserAgent","代理服务�?,"绕过代理的主�?,连接选项)

当前是否能正常访问互联网,所有参数可�?
### inet.http.status(url,noAutoRedirect,httpMethod)

�?@url 指定网址发送请求并返回 HTTP 状态码�?
如果未成功发送请求则返回 null�?
可选参�?@noAutoRedirect �?true 则禁止自动重定向，默认为 false�?
可选用 @httpMethod 参数指定 HTTP 请求方法，默认为 "HEAD"�?
大部分网址请求成功会返�?200 状态码�?
部分网址会返�?2xx 状态码，重定向返回 3xx 状态码�?
可用状态码请参�?inet.httpStatusCode �?
### inet.http.userAgent

创建 inet.http 对象且未明确指定 user agent 参数时使用的默认�?�?
适用�?inet.http 以及所有基�?inet.http 创建的对象，例如�?
inet.httpFile, inet.downBox, web.rest, inet.installer �?
## httpheadercontentObject 成员列表

### httpheadercontentObject.disposition.filename

下载文件�?
### httpheadercontentObject.disposition.type

文件类型,该值可能为�?

inline表示用于网页显示

attachment表示需要下载存储的附件

### httpheadercontentObject.type

返回MIME类型

## httprangeheadersObject 成员列表

### httprangeheadersObject.acceptRanges

如果值为�?bytes" 则表示该文件支持断点续传

### httprangeheadersObject.eTag

该文件唯一的标志�?用于验证

### httprangeheadersObject.lastModified

存放服务端文件的最后修改时�?用于验证

## inetHttpObject 成员列表

### inetHttpObject.\_defaultRequestErrHandle

```aardio aardio
inetHttpObject._defaultRequestErrHandle[0x2F06/*_ERROR_INTERNET_SEC_CERT_CN_INVALID*/] = function() {
    owner.setRequestOption(0x1F/*_INTERNET_OPTION_SECURITY_FLAGS*/,0x1000|0x2000|0x100|0x200|0x80);
    return true;/*添加 HTTP 请求错误处理程序，已清除错误并允许重试请返回 true */
}

```

### inetHttpObject.accept

指定可选择的文件类�?多个类型使用逗号分隔

默认无需指定,也可以在参数中指�?
### inetHttpObject.addHeaders

设置所有请求默认添加的HTTP�?
请求结束时不会清空此属�?
该值可以是 web.joinHeaders 函数支持的字符串、表（数组、键值对�?
### inetHttpObject.afterSend

```aardio aardio
inetHttpObject.afterSend = function(statusCode,contentLength){
    /*向服务器发送数据结束触发此回调函数
如果在这里读取全部HTTP头则会自动保存到 inetHttpObject.responseHeaders属�?即使结束请求所有读取HTTP头的函数将继续有�?/
    owner.readHeader();
}

```

### inetHttpObject.beforeSend

```aardio aardio
inetHttpObject.beforeSend = function(){
    /*已准备向服务器发送数据触发此回调函数*/
}

```

### inetHttpObject.beginRequest(url,method,referer,accept,flags,connectFlags)

打开连接并准备发送请�?
除URL以外,所有参数可�?
method参数指定HTTP请求方法�?
referer参数指定引用�?默认使用上一次访问的网址作为下一次的引用网址

accept指定客户端接受的MIME内容类型,参考HTTP请求头该字段说明

flags参数为\_INTERNET\_FLAG\_开头的常量用于指定请求选项,

connectFlags用于指定调打开连接选项,

flags,connectFlags一般用不到，详细的用法请参考此函数源码以及相关API文档

### inetHttpObject.beginSendData(数据长度)

发送请�?参数为待上传的数据总长�?默认�?

失败返回:null,错误信息,错误代码

### inetHttpObject.bufferSize

默认缓冲区大�?
默认�?0KB

### inetHttpObject.bufferTotal

上传数据总长�?
即beginSendData()参数传入的数�?
### inetHttpObject.close()

释放资源

http对象支持自动析构,即使不调用此函数资源也会自动释放

### inetHttpObject.codepage

设置post函数上传参数为表并转换为字符串时UrlEncode的输出代码页

### inetHttpObject.connectFlags

指定打开服务端连接的默认选项

此选项一般用户不需要了解，如果需要请参考beginRequest函数的源码以及相关API文档

### inetHttpObject.contentLength

send()函数执行后返回的文件长度

### inetHttpObject.disableCache()

强制刷新

可在参数中指定是否禁用缓�?
### inetHttpObject.disableCookies()

禁止自动添加、管理cookie的功�?

需要自行在HTTP请求头、响应头中分析处理cookie

可在参数中指定是否禁用cookies

### inetHttpObject.disableRedirects()

禁用重定�?
可在参数中指定是否禁用重定向

### inetHttpObject.down(url,postdata,headers,referer,accept,method,flags,connectFlags,noReceiveData)

发送请求并下载数据,get,post等调用此函数

不建议直接调用此函数，参�?

url:网址,除这个参数必须指定以外，后面其他参数都是可选参�?
postdata:提交数据

headers:http�?可以是web.joinHeaders支持的字符串、键值对、数组等格式

referer:http引用网址,默认使用上一次访问的网址作为下一次的引用网址

accept: 此参数用于HTTP请求头accept字段，用于指定可识别的内容类型列�?
flags: 用于设置请求选项,参考beginRequest函数说明

connectFlags:用于打开连接选项,参考beginRequest函数说明

noReceiveData: 指定为真则不下载服务器回应数�?
本地内部错误返回值为:null,错误信息,错误代码

服务端返回HTTP错误时返回值为:false,错误信息,HTTP错误代码

成功返回字符串对�?
### inetHttpObject.eachLine

```aardio aardio
for(str,size in inetHttpObject.eachLine() ){
    /*每次读取一行数据，忽略回车，去掉换行符*/
}

```

### inetHttpObject.eachRead

```aardio aardio
for(str,size in inetHttpObject.eachRead() ){
    /*循环读取数据，可选在 eachRead 的参数@1 指定缓冲区大�?/
}

```

### inetHttpObject.eachReadBuffer(缓冲�?长度)

```aardio aardio
var buffer = .raw.bufferc( 1024 * 10 );
for( size in inetHttpObject.eachReadBuffer( buffer ) ){

}

```

### inetHttpObject.enable(flags,enabled)

是否启用指定的请求选项

此函数修改对象的flags属�?但不会影响参数中未指定的选项

### inetHttpObject.endRequest()

关闭请求,与beginRequest配对使用.

### inetHttpObject.endSendData()

write()函数写完所有上传数据以�?

必须调用此函数结束上�?

成功返回: true,状态码,文件长度

出错返回:null,错误信息,错误代码

注意只有在调用此函数以后,才能使用其他读写HTTP头的函数.

### inetHttpObject.flags

```aardio aardio
inetHttpObject.flags = _INTERNET_FLAG_/*
指定打开网址请求的默认选项
禁用自动cookie管理请指定_INTERNET_FLAG_NO_COOKIE

此选项一般用户不需要了解，
请参考beginRequest函数的源码以及相关API文档
*/

```

### inetHttpObject.get(url,http�?引用网址,MIME)

向服务器发送GET请求并下载服务器返回的数�?

此函数会顺序调用 beginRequest(), send()�?
如果指定了onReceive回调函数,则调用该函数接收数据(成功返回true)

否则，调用readAll()等函数并返回下载数据�?
除URL�?其他为可选参�?
http头可以是web.joinHeaders支持的字符串、键值对、数组等格式

默认使用上一次访问的网址作为下一次的引用网址

本地内部错误返回值为:null,错误信息,错误代码

服务端返回HTTP错误时返回值为:false,错误信息,HTTP错误代码

成功返回字符串对�?
### inetHttpObject.getTime()

返回目标文件最后修改时�?不支持动态网�?

### inetHttpObject.getUserAgent()

返回HTTP客户端请求HTTP头中用户代理头的�?

该值可在创建HTTP客户端的构造参数中指定

### inetHttpObject.head

发�?HEAD 请求获取 HTTP �?
此函数不会直接返�?HTTP 头，

但函数返回后可使�?readHeader 函数读取 HTTP 响应�?
### inetHttpObject.head(url,http�?引用网址,MIME)

发�?HEAD 请求获取 HTTP �?
此函数不会直接返�?HTTP 头，

但函数返回后可使�?readHeader 函数读取 HTTP 响应�?
除URL�?其他为可选参�?
默认使用上一次访问的网址作为下一次的引用网址

本地内部错误返回值为:null,错误信息,错误代码,

服务端返�?HTTP 错误代码时返回值为:false�?
成功返回 true

### inetHttpObject.headEx(url,请求方法,提交数据,http�?引用网址,MIME)

使用指定的请求方法模拟HEAD方法,用于拒绝HEAD请求的网址

除网址以外所有参数可以省�?默认为使用GET方法

### inetHttpObject.headers

设置本次请求的HTTP�?
此属性会在每次发送请求以�?接收数据以前,初始化为空�?
该值可以是 web.joinHeaders 函数支持的字符串、表（数组、键值对�?
### inetHttpObject.lastReadErrCode

最后一次读取数据是否遇到错�?例如网络断开连接等等

### inetHttpObject.lastRequestUrl

最后一次请求成功的URL

### inetHttpObject.lastResponse()

获取最后一次服务器返回的原始数�?

仅在调用了readAll函数、或在get,post函数中间接调用readAll函数时设置该�?
### inetHttpObject.location(url,请求方法,提交数据,http�?引用网址,MIME)

获取最后一次重定向URL

如果省略url参数,则取最后一次请求成功的网址

如果发生了重定向,返回重定向后的网址

如果不存在重定向返回原网址

### inetHttpObject.mergeHeader("Name:value")

写入请求 HTTP �?

参数可以�?web.joinHeaders 函数支持的字符串、表（数组、键值）�?
如果存在同名 HTTP 头则合并�?
可使用第二个参数指定分隔符为逗号或分号，默认为逗号�?
函数执行成功返回 true

必须�?send 发送请求以前调�?

可在 beforeSend 事件内调�?
### inetHttpObject.onReceive

```aardio aardio
inetHttpObject.onReceive = function(str,size,contentLength){
    /*定义了此函数循环接收数据,�?get,post 等函数返回布尔�?/
}

```

### inetHttpObject.onReceiveBegin

```aardio aardio
inetHttpObject.onReceiveBegin = function(statusCode,contentLength){
    if( statusCode == 206/*断点续传*/  ){
        /*该事件函数在接收数据以前触发*/
    }
}

```

### inetHttpObject.onSend

```aardio aardio
inetHttpObject.onSend = function(remainSize){
    /*如果不指定上传数�?send函数会自动调用该函数获取数据直至此函数返回空值为�?/
    return str,len;
}

```

### inetHttpObject.onSendBegin

```aardio aardio
inetHttpObject.onSendBegin = function(){
    return len/*上传长度*/;
}

```

### inetHttpObject.parseStreamData

```aardio aardio
inetHttpObject.parseStreamData = function(data){
    /*如果 ContentType 响应类型�?text/event-stream�?�?eachRead �?onReceive 回调会自动调�?parseStreamData 提前转换数据�?如果 ContentType 响应类型�?application/x-ndjson�?�?onReceive 回调会自动调�?parseStreamData 提前转换数据
web.rest.client 会自动设定此回调*/
    return data;
}

```

### inetHttpObject.password

默认登录密码,

支持 Basic , Digest 认证

### inetHttpObject.post(url,post数据,http�?引用网址,MIME)

向服务器发送POST请求并下载服务器返回的数�?

如果post数据是一个表，则自动调用 inet.url.stringifyParameters 转换为字符串,

此函数会顺序调用 beginRequest(), send()�?
如果指定了onReceive回调函数,则调用该函数接收数据(成功返回true)

否则，调用readAll()等函数并返回下载数据�?
除URL与post数据以外,其他为可选参�?
http头可以是web.joinHeaders支持的字符串、键值对、数组等格式

默认使用上一次访问的网址作为下一次的引用网址

本地内部错误返回值为:null,错误信息,错误代码

服务端返回HTTP错误时返回值为:false,错误信息,HTTP错误代码

成功返回字符串对�?
### inetHttpObject.queryNumber(\_HTTP\_QUERY\_FLAG指定要返回的头信�?

取HTTP头数�?
### inetHttpObject.read(读取长度)

长度参数可�?
返回读取字符�?以及长度

失败返回false,错误信息

该函数必须在send请求以后调用

### inetHttpObject.readAll()

读取所有返回数�?
该函数必须在send请求以后调用

### inetHttpObject.readBuffer(buffer,写入长度)

下载文件数据

参数一必须是使�?buffer 对象

长度参数可�?默认为缓冲区长度

### inetHttpObject.readHeader

获取返回的HTTP�?
### inetHttpObject.readHeader("Content-Length:")

获取单个指定�?HTTP 服务器响应头，返回字符串�?
参数指定HTTP头名字或部分名字，忽略大小写，忽略冒号以后部分�?
必须�?send 发送请求以后才能调用此函数�?
如果调用 get,post,down 函数可在 afterSend 事件中调用此函数�?
默认在请求结束后此函数不可用�?
除非调用 head 函数发送请求，或调�?down 函数指定不返回数据，

则请求结�?readHeader 等读�?HTTP 头的函数仍然可用�?
如果无参数调用了此函数，则返回全部请求头（以回车换行作为分隔符）�?
并且直到下次请求以前，HTTP 响应头都会缓存在 responseHeaders 属性中�?
后续就可以自由使用所有读�?HTTP 头的函数

### inetHttpObject.readHeader()

获取服务器返回的 HTTP 响应头，

必须�?send 发送请求以后才能调用此函数�?
如果调用 get,post,down 函数可在 afterSend 事件中调用此函数�?
默认在请求结束后此函数不可用�?
除非调用 head 函数发送请求，或调�?down 函数指定不返回数据，

则请求结�?readHeader 等读�?HTTP 头的函数仍然可用�?
如果无参数调用了此函数，则返回全部请求头（以回车换行作为分隔符）�?
并且直到下次请求以前，HTTP 响应头都会缓存在 responseHeaders 属性中�?
后续就可以自由使用所有读�?HTTP 头的函数

### inetHttpObject.readHeaderContent()

读取HTTP头中文件下载相关信息

[返回对象:httpheadercontentObject](#httpheadercontentObject)

### inetHttpObject.readHeaderList("字符串参�?)

获取所有指定字符串作为开始段�?HTTP 头�?
忽略大小写，不忽略冒号以后部分�?
不指定参数则读取全部响应头�?
返回键值对组成的表对象，键名转为小写，每个值都是一个数组�?
必须�?send 发送请求以后才能调用此函数�?
如果调用 get,post,down 函数可在 afterSend 事件中调用此函数�?
默认在请求结束后此函数不可用�?
除非调用 head 函数发送请求，或调�?down 函数指定不返回数据，

则请求结�?readHeader 等读�?HTTP 头的函数仍然可用�?
如果无参数调用了此函数，则返回全部请求头（以回车换行作为分隔符）�?
并且直到下次请求以前，HTTP 响应头都会缓存在 responseHeaders 属性中�?
后续就可以自由使用所有读�?HTTP 头的函数

### inetHttpObject.readHeaderRange()

读取HTTP头中断点续传相关验证信息

[返回对象:httprangeheadersObject](#httprangeheadersObject)

### inetHttpObject.referer

引用页地址,此属性会自动设置为上次打开的网址

建议在参数中指定

### inetHttpObject.replaceHeader("Name:value")

写入请求 HTTP �?

参数可以�?web.joinHeaders 函数支持的字符串、表（数组、键值）�?
如果存在相同�?HTTP 头则覆盖，否则忽略�?
函数执行成功返回 true

必须�?send 发送请求以前调�?

可在 beforeSend 事件内调�?
### inetHttpObject.responseContentEncoding

应答HTTP头的Content-Encoding�?
如果该值为"gzip",通过readAll函数一次读取下载数据时会自动解�?

解压后该值将设为null�?
### inetHttpObject.responseContentType

每次发送请求后重置该值为服务器应答Content-Type�?
使用该值获取服务器返回的文档类�?
### inetHttpObject.responseHeaders

无参数调�?readHeader 函数时会保存HTTP头在该属性中

即使在请求结束以后，所有读取HTTP头的函数都可以继续使�?
调用head函数发送请求时会自动读取所有HTTP头到该属性中

该属性值每次发送新的请求前会自动清�?
### inetHttpObject.securityFlagIgnoreCertCnInvalid

HTTPS请求自动忽略无效CN名称

### inetHttpObject.securityFlagIgnoreCertDateInvalid

HTTPS请求自动忽略过期证书

### inetHttpObject.securityFlagIgnoreRevocation

忽略服务器证书吊销

### inetHttpObject.securityFlagIgnoreUnknownCa

HTTPS请求自动忽略无效CA证书

### inetHttpObject.securityFlagIgnoreWrongUsage

HTTPS请求自动忽略错误用法

### inetHttpObject.send(上传数据)

参数可�?调用beginSendData(上传数据),然后调用endSendData()

成功返回: true,状态码,文件长度

出错返回:null,错误信息,错误代码

### inetHttpObject.send(可选输入postdata)

此函数顺序调�?beginSendData() writeData() endSendData() 发送请�?
成功返回: true,状态码,文件长度

出错返回:null,错误信息,错误代码

### inetHttpObject.setAuth("用户�?,"密码")

为当前打开请求设置登录信息

成功返回true

### inetHttpObject.setProxyAuth("用户�?,"密码")

设置代理服务器登录用户名,密码

### inetHttpObject.setRequestOption( \_INTERNET\_OPTION, )

设置会话选项,

参数可以是数值或结构�?
用法参数MSDN

### inetHttpObject.setSessionOption( \_INTERNET\_OPTION, )

设置会话选项,

参数可以是数值或结构�?
用法参数MSDN

### inetHttpObject.setTimeouts(连接超时,请求超时,接收超时)

设置超时,以亳秒为单位(1秒为1000毫秒)

### inetHttpObject.statusCode

最后一次发送请求后服务端返回的HTTP状态码

100 ~ 101 为信息提�?
200 ~ 206 表示请求成功

300 ~ 305 表示重定�?
400 ~ 415 表求客户端请求出�?
500 ~ 505 表示服务端错�?
注意每次HTTP请求开始该值初始化为空,服务器应答后才会设置该�?
### inetHttpObject.username

默认登录用户�?

支持 Basic , Digest 认证

### inetHttpObject.writeBuffer(buffer,写入长度)

上传文件数据

参数一必须是使�?buffer 对象

长度参数可�?默认为缓冲区长度

### inetHttpObject.writeData(上传数据)

上传文件数据,支持一个或多个参数,

返回写入数据的总长�?失败返回空或0

调用此函数前必须调用beginSendData()

写完所有数据后 必须调用 endSendData();

### inetHttpObject.writeHeader("Name:value")

写入请求 HTTP �?

参数可以�?web.joinHeaders 函数支持的字符串、表（数组、键值）�?
如果存在相同�?HTTP 头则覆盖，否则添�?HTTP 头�?
函数执行成功返回 true

必须�?send 发送请求以前调�?

可在 beforeSend 事件内调�?
### inetHttpObject.writeHeaderRange(rangeHeaderInfo,开始位�?结束位置)

rangeHeaderInfo使用readHeaderRange()函数读取,

其它参数可�?开始位置默认为0,结束位置默认为文件尾

### 自动完成常量

\_HTTP\_ADDREQ\_FLAGS\_MASK=0xFFFF0000

\_HTTP\_ADDREQ\_FLAG\_ADD=0x20000000

\_HTTP\_ADDREQ\_FLAG\_COALESCE\_WITH\_COMMA=0x40000000

\_HTTP\_ADDREQ\_FLAG\_COALESCE\_WITH\_SEMICOLON=0x1000000

\_HTTP\_ADDREQ\_FLAG\_REPLACE=0x80000000

\_HTTP\_ADDREQ\_INDEX\_MASK=0xFFFF

\_INTERNET\_FLAG\_ASYNC=0x10000000

\_INTERNET\_FLAG\_CACHE\_ASYNC=0x80

\_INTERNET\_FLAG\_CACHE\_IF\_NET\_FAIL=0x10000

\_INTERNET\_FLAG\_DONT\_CACHE=0x4000000

\_INTERNET\_FLAG\_EXISTING\_CONNECT=0x20000000

\_INTERNET\_FLAG\_FORMS\_SUBMIT=0x40

\_INTERNET\_FLAG\_FROM\_CACHE=0x1000000

\_INTERNET\_FLAG\_FWD\_BACK=0x20

\_INTERNET\_FLAG\_HYPERLINK=0x400

\_INTERNET\_FLAG\_IDN\_DIRECT=0x1

\_INTERNET\_FLAG\_IDN\_PROXY=0x2

\_INTERNET\_FLAG\_IGNORE\_CERT\_CN\_INVALID=0x1000

\_INTERNET\_FLAG\_IGNORE\_CERT\_DATE\_INVALID=0x2000

\_INTERNET\_FLAG\_IGNORE\_REDIRECT\_TO\_HTTP=0x8000

\_INTERNET\_FLAG\_IGNORE\_REDIRECT\_TO\_HTTPS=0x4000

\_INTERNET\_FLAG\_KEEP\_CONNECTION=0x400000

\_INTERNET\_FLAG\_MAKE\_PERSISTENT=0x2000000

\_INTERNET\_FLAG\_MUST\_CACHE\_REQUEST=0x10

\_INTERNET\_FLAG\_NEED\_FILE=0x10

\_INTERNET\_FLAG\_NO\_AUTH=0x40000

\_INTERNET\_FLAG\_NO\_AUTO\_REDIRECT=0x200000

\_INTERNET\_FLAG\_NO\_CACHE\_WRITE=0x4000000

\_INTERNET\_FLAG\_NO\_COOKIES=0x80000

\_INTERNET\_FLAG\_NO\_UI=0x200

\_INTERNET\_FLAG\_OFFLINE=0x1000000

\_INTERNET\_FLAG\_PASSIVE=0x8000000

\_INTERNET\_FLAG\_PRAGMA\_NOCACHE=0x100

\_INTERNET\_FLAG\_RAW\_DATA=0x40000000

\_INTERNET\_FLAG\_READ\_PREFETCH=0x100000

\_INTERNET\_FLAG\_RELOAD=0x80000000

\_INTERNET\_FLAG\_RESTRICTED\_ZONE=0x20000

\_INTERNET\_FLAG\_RESYNCHRONIZE=0x800

\_INTERNET\_FLAG\_SECURE=0x800000

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/http.md)

