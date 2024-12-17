[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.rest.client 库模块帮助文�?
## web.rest 成员列表

### web.rest.client

REST客户�?
创建 REST 客户端�?
### web.rest.client()

[返回对象:webRestClientObject](client.html#webRestClientObject)

### web.rest.client(config)

创建 REST 客户端�?
可选用一个表参数指定 API 自定义的配置项�?
参数存为对象�?config 属性�?
### web.rest.client(userAgent,proxy,proxyBypass,httpFlags)

创建 REST 客户端，所有参数可选�?
userAgent 参数用于自定�?User-Agent 请求标头，用于服务器识别请求程序特征�?
HTTP 代理服务器请指定�?"代理服务器地址:端口" 格式�?
proxy 参数指定代理，proxyBypass 参数指定绕过代理的主机�?
└── [代理参数格式说明](../../../library-guide/std/inet/proxy.html)

httpFlags 可选用一个数值指�?HTTP 连接选项，一般不需要指定�?
可选传入一个表指定以上参数以及其他 API 自定义设置�?
如果传入表参数则存为对象�?config 属性�?
## webRestApiObject 成员列表

### webRestApiObject.?

可输入任�?HTTP API 资源�?
返回一�?HTTP API 调用对象,

返回对象可以使用成员操作符继续获取下级资源，

也可以作为函数直接调用并发送请�?

作为函数使用�?

可选用参数@1指定请求数据参表，也可直接指定请求字符串,

可选用参数@2指定URL参数�?

可选用参数 @2 �?@3 指定 inet.http对象�?onReceive 回调函数�?
指定 onReceive 回调函数则自动支持自动解�?SSE 流，兼容 ndjson 流�?
作为函数调用时成功返回解析后数据，失败返�?null,错误信息,错误代码

[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.delete()

DELETE方法提交请求,删除资源,

请求参数@1可以指定表或字符串、缓冲区,如果是表请求前会转换为字符串

可选用参数@2指定URL参数�?

可选用参数@3指定inet.http对象的onReceive回调函数

如果资源URL名称需要用�?delete，请使用\["/delete"\]替代以避免被识别为默认HTTP方法

### webRestApiObject.deleteDelete()

返回 HTTP API 调用对象�?
URL 资源名称�?HTTP 请求方法都设�?"get"

这是 delete\["/delete"\] 的缩略写�?
[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.get()

GET方法提交请求,获取资源,

请求参数@1可以指定表或字符串、缓冲区,如果是表请求前会转换为字符串

如果资源URL名称需要用�?get，请使用\["/get"\]替代以避免被识别为默认HTTP方法

### webRestApiObject.getGet()

返回 HTTP API 调用对象�?
URL 资源名称�?HTTP 请求方法都设�?"get"

这是 get\["/get"\] 的缩略写�?
[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.getUrl()

返回当前对象发送请求使用的 URL 地址�?
如果有远程函数与此函数同名，写为 \["/getUrl"\] 即可

### webRestApiObject.head()

HEAD方法提交请求

如果该函数返回非null值为成功,请使用lastResponseHeaders获取应答HTTP�?
请求参数可以指定表或字符�?如果是表请求前会转换为字符串

### webRestApiObject.headHead()

返回 HTTP API 调用对象�?
URL 资源名称�?HTTP 请求方法都设�?"get"

这是 head\["/head"\] 的缩略写�?
[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.patch()

PATCH方法提交请求,更新资源,

请求参数@1可以指定表或字符串、缓冲区,如果是表请求前会转换为字符串

可选用参数@2指定URL参数�?

可选用参数@3指定inet.http对象的onReceive回调函数

### webRestApiObject.patchPatch()

返回 HTTP API 调用对象�?
URL 资源名称�?HTTP 请求方法都设�?"get"

这是 patch\["/patch"\] 的缩略写�?
[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.post()

POST方法提交请求,新增或修改资�?

请求参数@1可以指定表或字符串、缓冲区,如果是表请求前会转换为字符串

可选用参数@2指定URL参数�?

可选用参数@3指定inet.http对象的onReceive回调函数

### webRestApiObject.postPost()

返回 HTTP API 调用对象�?
URL 资源名称�?HTTP 请求方法都设�?"get"

这是 post\["/post"\] 的缩略写�?
[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.put()

PUT方法提交请求,替换或更新资�?

请求参数@1可以指定表或字符串、缓冲区,如果是表请求前会转换为字符串

可选用参数@2指定URL参数�?

可选用参数@3指定inet.http对象的onReceive回调函数

### webRestApiObject.putPut()

返回 HTTP API 调用对象�?
URL 资源名称�?HTTP 请求方法都设�?"get"

这是 put\["/put"\] 的缩略写�?
[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.receiveFile

配置下次下载文件的参数，

此配置在后续�?get,post 等函数提交请求后自动清空

此函数成功返回对象自身，创建文件失败返回 null,错误信息

### webRestApiObject.receiveFile()

[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestApiObject.receiveFile(savePath,callback,saveDir)

配置下次下载文件的参数，

此配置在后续�?get,post 等函数提交请求后自动清空

此函数返回对象自�?
@savePath 参数指定下载文件路径�?
可选用 @saveDir 指定下载根目录，指定此参数则参数 @1 应为相对路径�?
可选用 @callback 参数指定下载进度回调函数,

进度回调函数参数依次�?recvData,recvSize,contentLength�?
其中 recvData 为本次下载的数据�?
recvSize 为本次下载的字节数，

contentLength 为需要下载的总字节数

### webRestApiObject.sendFile("上传文件路径",进度回调函数,MIME,分块大小)

```aardio aardio
webRestApiObject.sendFile( "上传文件路径"
    ,function(sendData,sendSize,contentLength,remainSize){
        /*上传进度回调函数以及其他参数都可以省略，
如果打开文件失败，sendFile 函数返回 null 与错误信息，
否则返回响应数据*/
    }
);

```

### webRestApiObject.sendMultipartForm(上传字段�?进度回调函数,分块大小)

```aardio aardio
webRestApiObject.sendMultipartForm( {
        file = "@/*上传文件路径字前必须添加@字符�?上传表单可添加多个字段，
上传进度回调函数以及其他参数都可以省�?/"
    },function(sendData,sendSize,contentLength,remainSize){
        ..io.print("正在上传",sendSize,contentLength);
    }
);

```

## webRestClientObject 成员列表

### webRestClientObject.?

web.rest.client 或继承自 web.rest.client 的对象的其他成员函数或属性�?
请查看相关库函数文档或源�?
### webRestClientObject.\_http

inet.http客户端，用于执行http请求

[返回对象:inetHttpObject](#inetHttpObject)

### webRestClientObject.acceptType

期望返回的MIME内容类型,多个类型用逗号分隔

### webRestClientObject.addHeaders

替换所有请求默认添加的HTTP�?
请求结束时不会清空此属�?
该值可以是一个字符串,也可以是键值对组成的table对象

### webRestClientObject.afterSend

```aardio aardio
webRestClientObject.afterSend = function(statusCode,contentLength){
    /*向服务器发送数据结束触发此回调函数*/
}

```

### webRestClientObject.afterStringifyRequestParameters(提交参数,代码�?

```aardio aardio
webRestClientObject.afterStringifyRequestParameters = function(params,codepage){
    /*此时参数 params 已转换为字符串并准备提交到服务器�?codepage 参数为请求数据使用的代码页�?必须用第一个返回值返回新�?params �?/
    return params;
}

```

### webRestClientObject.api

定义API对象，使用成员操作符或下标获取API对象的成员时将会自动转换为新的API对象

### webRestClientObject.api("网址模板","HTTP动词","模式�?)

网址模板可使�?{name}、{/name}、或 {...} 指定模板参数,

大括号内的参数名可使用英文字符或数字,

模板参数名首字符为斜杠（例如{/name}）表示使用实参替换后保留斜杠�?
{...} 表示不定个数的模板参�?如使用多个实参替换则自动使用斜杠拼接�?
默认在网址模板尾部自动添加 {...}

返回API对象使用下标指定模板实参�?
如果下标是字符串，按下标出现的前后顺序替换模板参数，

如果下标是表对象，则表中的键值对用于替换与键同名的模板参�?

可选用参数@2指定HTTP动词,默认值为"POST"

参数@3如果为模式串，则使用模式匹配转换响应数据并返回�?
参数@3如果为函数，则调用该函数转换转换响应数据并返回�?
参数@3如果为数组，则作为string.map的模式参数@2转换响应数据并返�?
### webRestClientObject.api("网址模板","HTTP动词","模式�?,HTTP选项)

可选在参数@4�?_INTERNET\_FLAG_ 前缀常量自定义http请求选项

其他参数用法同上

### webRestClientObject.api()

[返回对象:webRestApiObject](client.html#webRestApiObject)

### webRestClientObject.beforeRequestHeaders(提交参数,提交数据,请求网址,请求方法,请求类型)

```aardio aardio
webRestClientObject.beforeRequestHeaders = function(params,payload,url,httpMethod,contentType){
    /*每次请求前触发此函数�?params 参数为本次请求的提交参数�?payload 为转换为字符串格式的提交数据
url 参数为本次请求网址�?httpMethod 参数�?HTTP 方法（大写）�?contentType 参数为请求内容类型�?可选以字符串、数组、键值等 web.joinHeaders 函数支持的格式返�?HTTP 头�?*/
    return {};
}

```

### webRestClientObject.beforeSend

```aardio aardio
webRestClientObject.beforeSend = function(){
    /*已准备向服务器发送数据触发此回调函数*/
}

```

### webRestClientObject.beforeStringifyRequestParameters(提交参数,代码�?

```aardio aardio
webRestClientObject.beforeStringifyRequestParameters = function(params,codepage){
    /*可以在该函数中修改提交提交参数表,或在此添加默认参�?此函数在stringifyRequestParameters之前调用
参数可能是字符串或者表*/
    return params;
}

```

### webRestClientObject.charset

指定服务端使用的编码,默认�?UTF-8",

服务端HTTP响应头里如果显式指定了编码，会自动修改此属�?
对于服务端返回的数据,会根据charset自动转换为aardio默认的UTF8编码

对于请求参数,如果使用JSON编码统一转换为Unicode编码格式,不需要考虑编码转换,

如果使用UrlEncode编码与浏览器的规则一致，根据charset转换为对应编码后提交�?
开发服务端接口应统一使用UTF8编码,可避免任何乱码问�?
### webRestClientObject.checkResponseResult(result)

```aardio aardio
webRestClientObject.checkResponseResult = function(result){
    if(result[["errcode"]]==40014){
        var lastRequestInfo = http.lastRequestInfo;
        /*此函数在成功解析服务器响数数据后调用
可在此函数中检查token是否过期并重新发送请�?/
        return http.requestEx(lastRequestInfo);
    }

    return result;
}

```

### webRestClientObject.close()

关闭对象释放资源

### webRestClientObject.config

自定义的 API 配置表�?
默认指向创建对象时指定的表参数�?
如果构造对象未指定表参数，此配置默认为 null 值�?
### webRestClientObject.contentType

写入HTTP头ContentType属性的内容类型

设为null空�?或每次请求完成将自动重置为defaultContentType

### webRestClientObject.defaultContentType

默认内容类型

### webRestClientObject.defaultUrlTemplate

默认API网址模板

### webRestClientObject.delete(网址,参数�?

使用该DELETE方法提交请求,删除资源

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.encodeKey

自定义替�?API 网址变量值使用的编码函数,

此函数接收一个资源名参数,返回编码后的资源�?

必须在定�?API 对象之前指定,

默认已指定为 inet.url.encodeMbcs 函数

### webRestClientObject.endRequest()

可用于afterSend事件提前结束当前请求

### webRestClientObject.extraParameters

指定附加到所有请求参数中的默认参�?
该值应当是一个表,请求参数指定表对象时或为null才会附加extraParameters

### webRestClientObject.extraUrlParameters

指定附加到所有请�?URL 的默认参数�?
该值可以是一个表或字符串�?
表参数使�?inet.url.stringifyParameters 转换为字符串�?
表中的值如果是函数则每次请求都调用该函数取�?
### webRestClientObject.get(网址,参数�?

使用该GET方法提交请求,获取资源

请求参数将会自动转换为URL附加参数,

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.get(网址,参数�?接收数据回调函数)

使用该GET方法提交请求,获取资源

请求参数将会自动转换为URL附加参数,

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

如果服务端返回内容类型为 text/event-stream�?
则接收数据回调函数的参数为解析服务端每次推送数据的表对象，

否则回调参数依次为：当前响应数据，本次响应数据长度，响应数据总长�?
### webRestClientObject.getUserAgent()

返回HTTP客户端请求HTTP头中用户代理头的�?

该值可在创建HTTP客户端的构造参数中指定

### webRestClientObject.head(网址,参数�?

使用 HEAD 方法提交请求

如果该函数返回非 null 值为成功,请使�?lastResponseHeaders 获取应答HTTP头�?
成功返回 true,失败返回 null,错误信息,错误代码

### webRestClientObject.headGet(网址,参数�?

使用 GET 方法提交请求，但仅获�?HTTP 头�?
如果该函数返回非 null 值为成功,请使�?lastResponseHeaders 获取应答HTTP�?
成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.headPost(网址,参数�?

使用 POST 方法提交请求，但仅获�?HTTP 头�?
如果该函数返回非 null 值为成功,请使�?lastResponseHeaders 获取应答HTTP�?
成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.lastRequestInfo

最后一次请示使用的所有参数信�?
### webRestClientObject.lastRequestMethod

最后一次请示使用的HTTP方法

### webRestClientObject.lastRequestUrl

获取最后一次请求的URL

### webRestClientObject.lastResponse()

获取最后一次服务器返回的数�?

如果控制台已打开或在开发环境中导入 console 库则在控制台输出数据

下载文件时该值为�?
### webRestClientObject.lastResponseContentType

服务器响应头 Content-Type 的�?
### webRestClientObject.lastResponseError()

返回服务器最后一次返回的错误响应，并转换为错误对象�?
与调�?API 时转换响应数据一样，支持相同的服务器响应格式 �?
如果错误来自本地（lastStatusCode 属性为 null）则此函数返�?null �?
如果最后一次发生请求成功，则此函数返回 null �?
如果在参�?@1 中指定返回字段，且错误对象包含该字段则使用直接下标获取并返回字段值�?
获取字段失败返回 null 而非抛出异常

### webRestClientObject.lastResponseHeaderList("字符串参�?)

获取所有指定字符串作为开始段�?HTTP 头�?
忽略大小写，不忽略冒号以后部分�?
不指定参数则读取全部响应头�?
返回键值对组成的表对象，键名转为小写，每个值都是一个数组�?
如果调用 head, headGet, headPost 等函数�?
或调�?�?API 对象�?head.get,head.post 等函数，

则在请求成功后可调用此函数读�?HTTP �?
### webRestClientObject.lastResponseHeaders

获取返回�?HTTP 响应�?
### webRestClientObject.lastResponseHeaders("Content-Length:")

获取单个指定�?HTTP 服务器响应头，返回字符串�?
参数指定HTTP头名字或部分名字，忽略大小写，忽略冒号以后部分�?
如果调用 head, headGet, headPost 等函数�?
或调�?�?API 对象�?head.get,head.post 等函数，

则在请求成功后可调用此函数读�?HTTP �?
### webRestClientObject.lastResponseHeaders()

获取返回�?HTTP 响应头�?
如果调用 head, headGet, headPost 等函数�?
或调�?�?API 对象�?head.get,head.post 等函数，

则在请求成功后可调用此函数读�?HTTP �?
### webRestClientObject.lastResponseString()

获取最后一次服务器返回的原始数据，

请求失败，或者下载文件时此属性值为�?
### webRestClientObject.lastStatusCode

获取最近一次请求返回的HTTP状态码

100 ~ 101 为信息提�?
200 ~ 206 表示请求成功

300 ~ 305 表示重定�?
400 ~ 415 表求客户端请求出�?
500 ~ 505 表示服务端错�?
### webRestClientObject.lastStatusMessage()

获取最近返回的HTTP状态码文本描述

第二个返回值为状态码

### webRestClientObject.notify(回调函数)

```aardio aardio
webRestClientObject.notify(
    function(){
        /*在此回调函数中所有请求在发送数据后立即关闭连接*/
    }
)

```

### webRestClientObject.ok()

最后一次请求是否成�?
服务器应答并且状态码�?XX该函数返回真

### webRestClientObject.onAuthenticate

function(authHeader){
\_\_/\*请求遇到401错误触发此函�?

authHeader为服务器响应HTT头WWW-Authenticate的�?
登录成功请返回true以重新发送上次失败的请求\*/
}

### webRestClientObject.parseResponseResult(响应数据,单个流式数据�?

```aardio aardio
webRestClientObject.parseResponseResult = function(resp,streamChunk){
    /*用于解析服务器应答数据�?此函数一般由库文件定义，一般调用不应修改此函数�?resp 为服务器应答字符串，
streamChunk 指示是否�?SSE �?ndjson 流回调函数中解析单个�?/
    return resp;
}

```

### webRestClientObject.patch(网址,参数�?

使用该PATCH方法提交请求,更新资源

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.post(网址,参数�?

使用该POST方法提交请求,新增或修改资�?
请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.post(网址,参数�?接收数据回调函数)

使用该POST方法提交请求,新增或修改资�?
请求参数可以指定表或字符�?如果是表请求前会转换为字符串

如果服务端返回内容类型为 text/event-stream�?
则接收数据回调函数的参数为解析服务端每次推送数据的表对象，

否则回调参数依次为：当前响应数据，本次响应数据长度，响应数据总长�?
### webRestClientObject.put(网址,参数�?

使用该PUT方法提交请求,替换或更新资�?
请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.receiveFile

配置下次下载文件的参数，

此配置在后续�?get,post 等函数提交请求后自动清空

此函数成功返回对象自身，创建文件失败返回 null,错误信息

### webRestClientObject.receiveFile()

[返回对象:webRestClientObject](client.html#webRestClientObject)

### webRestClientObject.receiveFile(savePath,callback,saveDir)

配置下次下载文件的参数，

此配置在后续�?get,post 等函数提交请求后自动清空

此函数成功则返回对象自身

@savePath 参数指定下载文件路径�?
可选用 @saveDir 指定下载根目录，指定此参数则参数 @1 应为相对路径�?
### webRestClientObject.referer

引用页地址

如果此属性指定了一个值，则每次请求都会使用该引用�?
如果不指定，每次请求都会自动设置上次请求的网址为引用页

这个属性不像inet.http对象的referer属性那样每次请求结束都会清�?
### webRestClientObject.request

发送请�?

该函数不会解析URL中的模板参数

### webRestClientObject.request(网址,参数�?"HTTP动词",URL参数�?

除参数@1以外，其他所有参数都可以省略,

省略参数@3则使用默认的调用方法

成功返回数据,失败返回空�?错误信息,错误代码

### webRestClientObject.requestEx(lastRequstInfo)

用于重新发送请求，

参数必须指定当前对象的lastRequestInfo属�?
### webRestClientObject.sendFile("上传文件路径",进度回调函数)

```aardio aardio
webRestClientObject.sendFile( "上传文件路径"
    ,function(sendData,sendSize,contentLength,remainSize){
        /*上传进度回调函数以及其他参数都可以省略，
如果打开文件失败，sendFile 函数返回 null 与错误信息，
否则返回响应数据*/
    }
);

```

### webRestClientObject.sendFile()

[返回对象:webRestClientObject](client.html#webRestClientObject)

### webRestClientObject.sendMultipartForm()

[返回对象:webRestClientObject](client.html#webRestClientObject)

### webRestClientObject.sendMultipartForm(上传字段�?进度回调函数)

```aardio aardio
webRestClientObject.sendMultipartForm( {
        file = "@/*上传文件路径字前必须添加@字符�?上传表单可添加多个字段，
上传进度回调函数以及其他参数都可以省�?/"
    },function(sendData,sendSize,contentLength,remainSize){

    }
);

```

### webRestClientObject.setAuth

设置登录�?密码，或者设�?API Key �?Secret Key

### webRestClientObject.setAuth("API Key","Secret Key")

设置 API Key，Secret Key�?
此函数会清空 setAuthToken 设置的认证令牌（token�?
### webRestClientObject.setAuth("登录�?,"密码")

设置登录�?密码,

默认用于HTTP登录认证

,

支持 Basic , Digest 认证

此函数会清空 setAuthToken 设置的认证令牌（token�?
### webRestClientObject.setAuthToken

设置认证令牌（token�?
### webRestClientObject.setAuthToken(token,tokenType)

设置认证令牌（token）�?
@token 可指定令牌，也可以指定返回令牌的网址�?
@tokenType 为可选参数，默认�?Bearer"�?
如果指定了令牌，则会添加请求�?"Authorization:Bearer 令牌"�?
@tokenType 也可以指定为空字符串�?
此函数会清空 setAuth 设置的用户名与密�?
### webRestClientObject.setCookie

调用 inet.setCookie 设置 Cookies �?
web.rest,inet.http,web.form 等共�?Cookies 设置�?
此函数用法与 inet.setCookie 函数完全相同�?
这里仅列出几种常用的参数用法�?
其他用法请查�?inet.setCookie 函数说明

### webRestClientObject.setCookie("网址","�?,"�?,过期时间或天�?

设定指定网址�?Cookie�?
第一个参数指�?Cookie 生效的网址�?
如果不指定值则删除删除指定名字的会�?cookie 与持�?Cookie�?
如果指定名字与值则设置 Cookie，如果不指定过期时间则仅设置会话 Cookie�?
否则设置为持�?Cookie�?
可选参�?@4 使用 time 对象指定过期时间，或用数值指定过期天�?
### webRestClientObject.setCookie(webView)

传入 web.view 可直接获取浏览器控件�?Cookies

作为 inet.setCookie 的参数，设置�?inet.http 可用�?Cookies �?
web.form,web.rest,inet.http 共享�?Cookies 设置

### webRestClientObject.setHeaders

设置所有请求默认添加的HTTP�?
### webRestClientObject.setHeaders(headers)

参数 @headers 必须指定一个表�?

用该表中的键值对更新 addHeaders 属性中的键�?
如果addHeaders的原属性值不是一个表,则先清空该属�?
### webRestClientObject.strictParsing

对于 JSON 客户端，如果此属性设�?true�?
且服务器响应头未声明 JSON 类型，返回数据第一个字符不�?{ 也不�?\[�?
则直接返回包含服务器响应数据的字符串�?
此属性值默认为 null

### webRestClientObject.stringifyRequestParameters(提交参数�?代码�?

```aardio aardio
webRestClientObject.stringifyRequestParameters = function(params,codepage){
    /*参数是表对象时调用此函数转换为字符串
此函数一般由库文件定义，一般调用不应修改此函数
注意返回的文本格式应�?owner.contentType 一�?在该函数中可获取或修改对象的 lastRequestUrl, lastRequestMethod 属�?/
    return params;
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.md')

