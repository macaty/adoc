[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# inet.whttp 库模块帮助文�?
说明

inet.http �?inet.whttp 用法与接口基本相同，一般可相互替代�?普通桌面客户端软件(非NT服务)请使�?inet.http（WinINet�?而不应该使用 inet.whttp（WinHTTP）�?
inet.whttp 并非�?inet.http 那样可以获取 IE 的默认代理设�?也不�?inet.setProxy 函数的影�?
inet.whttp 的默认代理需要使用函�?WinHttpSetDefaultProxyConfiguration 修改,而调用这�?API 则需要管理权�?
您可以在创建 inet.whttp 对象时指定代理服务器参数�?IE",aardio 将自动获取IE代理设置�?
WinHTTP 错误代码说明
[https://docs.microsoft.com/zh-cn/windows/win32/winhttp/error-messages](https://docs.microsoft.com/zh-cn/windows/win32/winhttp/error-messages)

## inet 成员列表

### inet.whttp("UserAgent","HTTP://代理服务器IP:端口","绕过代理主机",选项)

所有参数可以省�?

UserAgent参数指定发送给服务器的程序�?

代理指定空字符串为使用默认代�?如果代理设为"IE"则使用IE以及inet.setProxy的代理设�?
### inet.whttp()

[返回对象:inetWhttpObject](#inetWhttpObject)

## inet.whttp 成员列表

WinHTTP支持�?
多对象会话cookie隔离不共�?不支持持久化cookie

不与浏览器控件等共享cookie与代理设�?

支持NT服务

创建HTTP会话对象,所有参数可选，

注意提前导入zlib库，readAll 函数才能支持 gzip 自动解压�?
### inet.whttp.get(url,headers,referer)

用于界面线程创建线程并获�?@url 指定网址的数�?

此函数等待下载完成但不会阻塞界面消息循环,

可选用 @headers 指定 HTTP �?

可选用 @referer 指定引用网址,

所有参数用法与 格式请参�?inet.whttp 对象�?get 函数相同

### inet.whttp.setProxy("HTTP://代理IP:端口")

修改默认代理设置,进程有效

### inet.whttp.setProxy("IE")

whttp自动获取inet.setProxy或IE代理服务器设�?进程有效

### inet.whttp.setProxy()

使用WinHTTP的系统默认代理设�?
可用API:WinHttpSetDefaultProxyConfiguration修改设置,需管理权限

### inet.whttp.setProxy(false)

whttp默认禁用代理,进程有效

### inet.whttp.status(url,noAutoRedirect,httpMethod)

�?@url 指定网址发送请求并返回 HTTP 状态码�?
如果未成功发送请求则返回 null�?
可选参�?@noAutoRedirect �?true 则禁止自动重定向，默认为 false�?
可选用 @httpMethod 参数指定 HTTP 请求方法，默认为 "HEAD"�?
大部分网址请求成功会返�?200 状态码�?
部分网址会返�?2xx 状态码，重定向返回 3xx 状态码�?
可用状态码请参�?inet.httpStatusCode �?
### inet.whttp.userAgent

创建 inet.whttp 对象且未明确指定 user agent 参数时使用的默认�?
## inetWhttpObject 成员列表

### inetWhttpObject.\_defaultRequestErrHandle

```aardio aardio
inetWhttpObject._defaultRequestErrHandle[12175/*_ERROR_WINHTTP_SECURE_FAILURE*/ ] = function() {
    owner.setRequestOption(0x1F/*_WINHTTP_OPTION_SECURITY_FLAGS*/,0x1000|0x2000|0x100|0x200);
    return true;/*添加 HTTP 请求错误处理程序，已清除错误并允许重试请返回 true */
}

```

### inetWhttpObject.accept

指定可选择的文件类�?
默认无需指定,也可以在参数中指�?
### inetWhttpObject.addHeaders

设置所有请求默认添加的HTTP�?
请求结束时不会清空此属�?
该值可以是 web.joinHeaders 函数支持的字符串、表（数组、键值对�?
### inetWhttpObject.afterSend

```aardio aardio
inetWhttpObject.afterSend = function(statusCode,contentLength){
    /*向服务器发送数据结束触发此回调函数
如果在这里读取全部HTTP头则会自动保存到 inetWhttpObject.responseHeaders属�?即使结束请求所有读取HTTP头的函数将继续有�?/
    owner.readHeader();
}

```

### inetWhttpObject.beforeSend

```aardio aardio
inetWhttpObject.beforeSend = function(){
    /*已准备向服务器发送数据触发此回调函数*/
}

```

### inetWhttpObject.beginRequest(url,method,referer,accept,flags,connectFlags)

打开连接并准备发送请�?
除URL以外,所有参数可�?
method参数指定HTTP请求方法�?
referer参数指定引用�?默认使用上一次访问的网址作为下一次的引用网址

accept指定客户端接受的MIME内容类型,参考HTTP请求头该字段说明

flags参数用于指定请求选项,

connectFlags用于指定调打开连接选项,

flags,connectFlags一般用不到，详细的用法请参考此函数源码以及相关API文档

### inetWhttpObject.beginSendData(数据总长�?

发送请�?参数为待上传的数据总长�?默认�?

失败返回:null,错误信息,错误代码

### inetWhttpObject.bufferSize

默认缓冲区大�?
默认根据下载速度自动调整该大�?
### inetWhttpObject.bufferTotal

上传数据总长�?
即beginSendData()参数传入的数�?
### inetWhttpObject.close()

释放资源

whttp对象支持自动析构,即使不调用此函数资源也会自动释放

### inetWhttpObject.codepage

设置post函数上传参数为表并转换为字符串时UrlEncode的输出代码页

### inetWhttpObject.connectFlags

指定打开服务端连接的默认选项

此选项一般用户不需要了解，如果需要请参考beginRequest函数的源码以及相关API文档

### inetWhttpObject.contentLength

send()函数执行后返回的文件长度

### inetWhttpObject.disable(\_WINHTTP\_DISABLE)

禁用指定功能

必须在beginRequest()之后调用

### inetWhttpObject.disableCache()

强制刷新

### inetWhttpObject.disableCookies()

禁止自动添加、管理cookie的功�?

需要自行在HTTP请求头、响应头中分析处理cookie

### inetWhttpObject.disableRedirects()

禁止重定�?
### inetWhttpObject.down(url,postdata,headers,referer,accept,method,flags,connectFlags,noReceiveData)

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
### inetWhttpObject.eachLine

```aardio aardio
for(str,size in inetWhttpObject.eachLine() ){
    /*每次读取一行数据，忽略回车，去掉换行符*/
}

```

### inetWhttpObject.eachRead

```aardio aardio
for(str,size in inetWhttpObject.eachRead() ){
    /*循环读取数据，可选在 eachRead 的参数@1 指定缓冲区大�?/
}

```

### inetWhttpObject.eachReadBuffer(缓冲�?长度)

```aardio aardio
var buffer = .raw.bufferc( 1024 * 10 );
for( size in inetWhttpObject.eachReadBuffer( buffer ) ){

}

```

### inetWhttpObject.endRequest()

关闭请求,与beginRequest配对使用.

### inetWhttpObject.endSendData()

wirte()函数写完所有上传数据以�?

必须调用此函数结束上�?

成功返回: true,状态码,文件长度

出错返回:null,错误信息,错误代码

### inetWhttpObject.flags

```aardio aardio
inetWhttpObject.flags = _WINHTTP_FLAG_/*
指定打开网址请求的默认选项
此选项一般用户不需要了解，
请参考beginRequest函数的源码以及相关API文档
*/

```

### inetWhttpObject.get(url,http�?引用网址,MIME)

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
### inetWhttpObject.getUserAgent()

返回HTTP客户端请求HTTP头中用户代理头的�?

该值可在创建HTTP客户端的构造参数中指定

### inetWhttpObject.head

发�?HEAD 请求获取 HTTP �?
此函数不会直接返�?HTTP 头，

但函数返回后可使�?readHeader 函数读取 HTTP 响应�?
### inetWhttpObject.head(url,http�?引用网址,MIME)

发�?HEAD 请求获取 HTTP �?
此函数不会直接返�?HTTP 头，

但函数返回后可使�?readHeader 函数读取 HTTP 响应�?
除URL�?其他为可选参�?
默认使用上一次访问的网址作为下一次的引用网址

本地内部错误返回值为:null,错误信息,错误代码,

服务端返�?HTTP 错误代码时返回值为:false�?
成功返回 true

### inetWhttpObject.headEx(url,请求方法,提交数据,http�?引用网址,MIME)

使用指定的请求方法模拟HEAD方法,用于拒绝HEAD请求的网址

除网址以外所有参数可以省�?默认为使用GET方法

### inetWhttpObject.headers

设置本次请求的HTTP�?
此属性会在每次发送请求以�?接收数据以前,初始化为空�?
该值可以是 web.joinHeaders 函数支持的字符串、表（数组、键值对�?
### inetWhttpObject.lastReadErrCode

最后一次读取数据是否遇到错�?例如网络断开连接等等

### inetWhttpObject.lastRequestUrl

最后一次请求成功的URL

### inetWhttpObject.lastResponse()

获取最后一次服务器返回的原始数�?

仅在调用了readAll函数、或在get,post函数中间接调用readAll函数时设置该�?
### inetWhttpObject.location(url,请求方法,提交数据,http�?引用网址,MIME)

获取最后一次重定向URL

如果省略url参数,则取最后一次请求成功的网址

如果发生了重定向,返回重定向后的网址

如果不存重定向返回原网址

### inetWhttpObject.mergeHeader("Name:value")

写入请求 HTTP �?

参数可以�?web.joinHeaders 函数支持的字符串、表（数组、键值）�?
如果存在同名 HTTP 头则合并�?
可使用第二个参数指定分隔符为逗号或分号，默认为逗号�?
函数执行成功返回 true

必须�?send 发送请求以前调�?

可在 beforeSend 事件内调�?
### inetWhttpObject.onReceive

```aardio aardio
inetWhttpObject.onReceive = function(str,size,contentLength){
    /*定义了此函数循环接收数据,�?get,post 等函数返回布尔�?/
}

```

### inetWhttpObject.onReceiveBegin

```aardio aardio
inetWhttpObject.onReceiveBegin = function(statusCode,contentLength){
    if( statusCode == 206 /*断点续传*/  ){
        /*该事件函数在接收数据以前触发*/
    }
}

```

### inetWhttpObject.onSend

```aardio aardio
inetWhttpObject.onSend = function(remainSize){
    /*如果不指定上传数�?send函数会自动调用该函数获取数据直至此函数返回空值为�?/
    return str,len;
}

```

### inetWhttpObject.onSendBegin

```aardio aardio
inetWhttpObject.onSendBegin = function(){
    return len/*上传长度*/;
}

```

### inetWhttpObject.parseStreamData

```aardio aardio
inetWhttpObject.parseStreamData = function(data){
    /*如果 ContentType 响应类型�?text/event-stream�?�?eachRead �?onReceive 回调会自动调�?parseStreamData 提前转换数据�?如果 ContentType 响应类型�?application/x-ndjson�?�?onReceive 回调会自动调�?parseStreamData 提前转换数据
web.rest.client 会自动设定此回调*/
    return data;
}

```

### inetWhttpObject.password

默认登录密码,

支持 Basic , Digest 认证

### inetWhttpObject.post(url,post数据,http�?引用网址,MIME)

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
### inetWhttpObject.queryNumber(\_HTTP\_QUERY\_FLAG指定要返回的头信�?

取HTTP头数�?
### inetWhttpObject.read(读取长度)

长度参数可�?
返回读取字符�?以及长度

该函数必须在send请求以后调用

### inetWhttpObject.readAll()

读取所有返回数�?
该函数必须在send请求以后调用

### inetWhttpObject.readBuffer(buffer,写入长度)

下载文件数据

参数一必须是使�?buffer 对象

长度参数可�?默认为缓冲区长度

### inetWhttpObject.readHeader

获取返回的HTTP�?
### inetWhttpObject.readHeader("Content-Length:")

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

### inetWhttpObject.readHeader()

获取服务器返回的 HTTP 响应头，

必须�?send 发送请求以后才能调用此函数�?
如果调用 get,post,down 函数可在 afterSend 事件中调用此函数�?
默认在请求结束后此函数不可用�?
除非调用 head 函数发送请求，或调�?down 函数指定不返回数据，

则请求结�?readHeader 等读�?HTTP 头的函数仍然可用�?
如果无参数调用了此函数，则返回全部请求头（以回车换行作为分隔符）�?
并且直到下次请求以前，HTTP 响应头都会缓存在 responseHeaders 属性中�?
后续就可以自由使用所有读�?HTTP 头的函数

### inetWhttpObject.readHeaderContent()

读取HTTP头中文件下载相关信息

该函数在调用send函数以后或afterSend事件中可�?
调用head函数发送请求成功以�?则请求结束后该函数仍然可�?
[返回对象:httpheadercontentObject](#httpheadercontentObject)

### inetWhttpObject.readHeaderList("字符串参�?)

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

### inetWhttpObject.readHeaderRange()

读取HTTP头中断点续传相关验证信息

### inetWhttpObject.referer

引用页地址,此属性会自动设置为上次打开的网址

建议在参数中指定

请不要使�?Referer 请求头指定引用地址�?
应使�?referer 参数或属性修改引用页

### inetWhttpObject.replaceHeader("Name:value")

写入请求 HTTP �?

参数可以�?web.joinHeaders 函数支持的字符串、表（数组、键值）�?
如果存在相同�?HTTP 头则覆盖，否则忽略�?
函数执行成功返回 true

必须�?send 发送请求以前调�?

可在 beforeSend 事件内调�?
### inetWhttpObject.responseContentEncoding

应答HTTP头的Content-Encoding�?
如果该值为"gzip",通过readAll函数一次读取下载数据时会自动解�?

解压后该值将设为null�?
### inetWhttpObject.responseContentType

每次发送请求后重置该值为服务器应答Content-Type�?
使用该值获取服务器返回的文档类�?
### inetWhttpObject.responseHeaders

无参数调�?readHeader 函数时会保存HTTP头在该属性中

即使在请求结束以后，所有读取HTTP头的函数都可以继续使�?
调用head函数发送请求时会自动读取所有HTTP头到该属性中

该属性值每次发送新的请求前会自动清�?
### inetWhttpObject.securityFlagIgnoreCertCnInvalid

HTTPS请求自动忽略无效CN名称

### inetWhttpObject.securityFlagIgnoreCertDateInvalid

HTTPS请求自动忽略过期证书

### inetWhttpObject.securityFlagIgnoreUnknownCa

HTTPS请求自动忽略无效CA证书

### inetWhttpObject.securityFlagIgnoreWrongUsage

忽略用法不正确的问题

### inetWhttpObject.send(上传数据)

参数可�?调用beginSendData(上传数据),然后调用endSendData()

成功返回: true,状态码,文件长度

出错返回:null,错误信息,错误代码

### inetWhttpObject.send(可选输入postdata)

此函数顺序调�?beginSendData() writeData() endSendData() 发送请�?
成功返回: true,状态码,文件长度

出错返回:null,错误信息,错误代码

### inetWhttpObject.setAuth("用户�?,"密码")

为当前打开请求设置登录信息

成功返回true

### inetWhttpObject.setProxyAuth("用户�?,"密码")

设置代理服务器登录用户名,密码

### inetWhttpObject.setRequestOption( \_WINHTTP\_OPTION, )

设置会话选项,

参数可以是数值或结构�?
用法参数MSDN

### inetWhttpObject.setSessionOption( \_WINHTTP\_OPTION, )

设置会话选项,

参数可以是数值或结构�?
用法参数MSDN

### inetWhttpObject.setTimeouts(连接超时,请求超时,接收超时)

设置超时,以亳秒为单位(1秒为1000毫秒)

### inetWhttpObject.statusCode

最后一次发送请求后服务端返回的HTTP状态码

100 ~ 101 为信息提�?
200 ~ 206 表示请求成功

300 ~ 305 表示重定�?
400 ~ 415 表求客户端请求出�?
500 ~ 505 表示服务端错�?
注意每次HTTP请求开始该值初始化为空,服务器应答后才会设置该�?
### inetWhttpObject.username

默认登录用户�?

支持 Basic , Digest 认证

### inetWhttpObject.writeBuffer(buffer,写入长度)

上传文件数据

参数一必须是使�?buffer 对象

长度参数可�?默认为缓冲区长度.

### inetWhttpObject.writeData(上传数据)

上传文件数据,支持一个或多个参数,

返回写入数据的总长�?失败返回空或0

调用此函数前必须调用beginSendData()

写完所有数据后 必须调用 endSendData();

### inetWhttpObject.writeHeader("Name:value")

写入请求 HTTP �?

参数可以�?web.joinHeaders 函数支持的字符串、表（数组、键值）�?
如果存在相同�?HTTP 头则覆盖，否则添�?HTTP 头�?
函数执行成功返回 true

必须�?send 发送请求以前调�?

可在 beforeSend 事件内调�?
### inetWhttpObject.writeHeaderRange(rangeHeaderInfo,开始位�?结束位置)

rangeHeaderInfo使用readHeaderRange()函数读取,

其它参数可�?开始位置默认为0,结束位置默认为文件尾

### 自动完成常量

\_SECURITY\_FLAG\_IGNORE\_CERT\_CN\_INVALID=0x1000

\_SECURITY\_FLAG\_IGNORE\_CERT\_DATE\_INVALID=0x2000

\_SECURITY\_FLAG\_IGNORE\_CERT\_WRONG\_USAGE=0x200

\_SECURITY\_FLAG\_IGNORE\_UNKNOWN\_CA=0x100

\_WINHTTP\_ADDREQ\_FLAGS\_MASK=0xFFFF0000

\_WINHTTP\_ADDREQ\_FLAG\_ADD=0x20000000

\_WINHTTP\_ADDREQ\_FLAG\_ADD\_IF\_NEW=0x10000000

\_WINHTTP\_ADDREQ\_FLAG\_COALESCE\_WITH\_COMMA=0x40000000

\_WINHTTP\_ADDREQ\_FLAG\_COALESCE\_WITH\_SEMICOLON=0x1000000

\_WINHTTP\_ADDREQ\_FLAG\_REPLACE=0x80000000

\_WINHTTP\_ADDREQ\_INDEX\_MASK=0xFFFF

\_WINHTTP\_AUTH\_SCHEME\_BASIC=1

\_WINHTTP\_AUTH\_SCHEME\_DIGEST=8

\_WINHTTP\_AUTH\_SCHEME\_NEGOTIATE=0x10

\_WINHTTP\_AUTH\_SCHEME\_NTLM=2

\_WINHTTP\_AUTH\_SCHEME\_PASSPORT=4

\_WINHTTP\_AUTH\_TARGET\_PROXY=1

\_WINHTTP\_AUTH\_TARGET\_SERVER=0

\_WINHTTP\_AUTOLOGON\_SECURITY\_LEVEL\_DEFAULT=0x0

\_WINHTTP\_AUTOLOGON\_SECURITY\_LEVEL\_HIGH=0x2

\_WINHTTP\_AUTOLOGON\_SECURITY\_LEVEL\_LOW=0x1

\_WINHTTP\_AUTOLOGON\_SECURITY\_LEVEL\_MEDIUM=0x0

\_WINHTTP\_CONNS\_PER\_SERVER\_UNLIMITED=0xFFFFFFFF

\_WINHTTP\_DISABLE\_AUTHENTICATION=0x4

\_WINHTTP\_DISABLE\_COOKIES=0x1

\_WINHTTP\_DISABLE\_KEEP\_ALIVE=0x8

\_WINHTTP\_DISABLE\_PASSPORT\_AUTH=0x0

\_WINHTTP\_DISABLE\_PASSPORT\_KEYRING=0x20000000

\_WINHTTP\_DISABLE\_REDIRECTS=0x2

\_WINHTTP\_DISABLE\_SPN\_SERVER\_PORT=0x0

\_WINHTTP\_ENABLE\_PASSPORT\_AUTH=0x10000000

\_WINHTTP\_ENABLE\_PASSPORT\_KEYRING=0x40000000

\_WINHTTP\_ENABLE\_SPN\_SERVER\_PORT=0x1

\_WINHTTP\_ENABLE\_SSL\_REVERT\_IMPERSONATION=0x2

\_WINHTTP\_ENABLE\_SSL\_REVOCATION=0x1

\_WINHTTP\_FIRST\_OPTION=0x1

\_WINHTTP\_FLAG\_BYPASS\_PROXY\_CACHE=0x100

\_WINHTTP\_FLAG\_ESCAPE\_DISABLE=0x40

\_WINHTTP\_FLAG\_ESCAPE\_DISABLE\_QUERY=0x80

\_WINHTTP\_FLAG\_ESCAPE\_PERCENT=0x4

\_WINHTTP\_FLAG\_NULL\_CODEPAGE=0x8

\_WINHTTP\_FLAG\_REFRESH=0x100

\_WINHTTP\_FLAG\_SECURE=0x800000

\_WINHTTP\_LAST\_OPTION=0x6C

\_WINHTTP\_OPTION\_AUTOLOGON\_POLICY=0x4D

\_WINHTTP\_OPTION\_CALLBACK=0x1

\_WINHTTP\_OPTION\_CLIENT\_CERT\_CONTEXT=0x2F

\_WINHTTP\_OPTION\_CLIENT\_CERT\_ISSUER\_LIST=0x5E

\_WINHTTP\_OPTION\_CODEPAGE=0x44

\_WINHTTP\_OPTION\_CONFIGURE\_PASSPORT\_AUTH=0x53

\_WINHTTP\_OPTION\_CONNECTION\_INFO=0x5D

\_WINHTTP\_OPTION\_CONNECT\_RETRIES=0x4

\_WINHTTP\_OPTION\_CONNECT\_TIMEOUT=0x3

\_WINHTTP\_OPTION\_CONTEXT\_VALUE=0x2D

\_WINHTTP\_OPTION\_DISABLE\_FEATURE=0x3F

\_WINHTTP\_OPTION\_ENABLETRACING=0x55

\_WINHTTP\_OPTION\_ENABLE\_FEATURE=0x4F

\_WINHTTP\_OPTION\_EXTENDED\_ERROR=0x18

\_WINHTTP\_OPTION\_GLOBAL\_PROXY\_CREDS=0x61

\_WINHTTP\_OPTION\_GLOBAL\_SERVER\_CREDS=0x62

\_WINHTTP\_OPTION\_HANDLE\_TYPE=0x9

\_WINHTTP\_OPTION\_HTTP\_VERSION=0x3B

\_WINHTTP\_OPTION\_IS\_PROXY\_CONNECT\_RESPONSE=0x68

\_WINHTTP\_OPTION\_MAX\_CONNS\_PER\_1\_0\_SERVER=0x4A

\_WINHTTP\_OPTION\_MAX\_CONNS\_PER\_SERVER=0x49

\_WINHTTP\_OPTION\_MAX\_HTTP\_AUTOMATIC\_REDIRECTS=0x59

\_WINHTTP\_OPTION\_MAX\_HTTP\_STATUS\_CONTINUE=0x5A

\_WINHTTP\_OPTION\_MAX\_RESPONSE\_DRAIN\_SIZE=0x5C

\_WINHTTP\_OPTION\_MAX\_RESPONSE\_HEADER\_SIZE=0x5B

\_WINHTTP\_OPTION\_PARENT\_HANDLE=0x15

\_WINHTTP\_OPTION\_PASSPORT\_COBRANDING\_TEXT=0x51

\_WINHTTP\_OPTION\_PASSPORT\_COBRANDING\_URL=0x52

\_WINHTTP\_OPTION\_PASSPORT\_RETURN\_URL=0x57

\_WINHTTP\_OPTION\_PASSPORT\_SIGN\_OUT=0x56

\_WINHTTP\_OPTION\_PASSWORD=0x1001

\_WINHTTP\_OPTION\_PROXY=0x26

\_WINHTTP\_OPTION\_PROXY\_PASSWORD=0x1003

\_WINHTTP\_OPTION\_PROXY\_SPN\_USED=0x6B

\_WINHTTP\_OPTION\_PROXY\_USERNAME=0x1002

\_WINHTTP\_OPTION\_READ\_BUFFER\_SIZE=0xC

\_WINHTTP\_OPTION\_RECEIVE\_PROXY\_CONNECT\_RESPONSE=0x67

\_WINHTTP\_OPTION\_RECEIVE\_RESPONSE\_TIMEOUT=0x7

\_WINHTTP\_OPTION\_RECEIVE\_TIMEOUT=0x6

\_WINHTTP\_OPTION\_REDIRECT\_POLICY=0x58

\_WINHTTP\_OPTION\_REDIRECT\_POLICY\_ALWAYS=0x2

\_WINHTTP\_OPTION\_REDIRECT\_POLICY\_DEFAULT=0x1

\_WINHTTP\_OPTION\_REDIRECT\_POLICY\_DISALLOW\_HTTPS\_TO\_HTTP=0x1

\_WINHTTP\_OPTION\_REDIRECT\_POLICY\_LAST=0x2

\_WINHTTP\_OPTION\_REDIRECT\_POLICY\_NEVER=0x0

\_WINHTTP\_OPTION\_REJECT\_USERPWD\_IN\_URL=0x64

\_WINHTTP\_OPTION\_REQUEST\_PRIORITY=0x3A

\_WINHTTP\_OPTION\_RESOLVE\_TIMEOUT=0x2

\_WINHTTP\_OPTION\_SECURE\_PROTOCOLS=0x54

\_WINHTTP\_OPTION\_SECURITY\_CERTIFICATE\_STRUCT=0x20

\_WINHTTP\_OPTION\_SECURITY\_FLAGS=0x1F

\_WINHTTP\_OPTION\_SECURITY\_KEY\_BITNESS=0x24

\_WINHTTP\_OPTION\_SEND\_TIMEOUT=0x5

\_WINHTTP\_OPTION\_SERVER\_CBT=0x6C

\_WINHTTP\_OPTION\_SERVER\_CERT\_CONTEXT=0x4E

\_WINHTTP\_OPTION\_SERVER\_SPN\_USED=0x6A

\_WINHTTP\_OPTION\_SPN=0x60

\_WINHTTP\_OPTION\_SPN\_MASK=0x1

\_WINHTTP\_OPTION\_UNLOAD\_NOTIFY\_EVENT=0x63

\_WINHTTP\_OPTION\_URL=0x22

\_WINHTTP\_OPTION\_USERNAME=0x1000

\_WINHTTP\_OPTION\_USER\_AGENT=0x29

\_WINHTTP\_OPTION\_USE\_GLOBAL\_SERVER\_CREDENTIALS=0x65

\_WINHTTP\_OPTION\_WORKER\_THREAD\_COUNT=0x50

\_WINHTTP\_OPTION\_WRITE\_BUFFER\_SIZE=0xD

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/inet/whttp.md)

