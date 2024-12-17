[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.wxmp.view 库模块帮助文�?
说明

用户信息字段�?user\_remark //备注
user\_comment\_cnt //留言�?user\_selected\_comment\_cnt //精选留言�?user\_reward\_cnt //点赞�?user\_reward\_money //赞赏金额，以分为单位
user\_openid //openid
user\_name //用户�?user\_msg\_cnt //发消息数
user\_city //所在城�?user\_province //所在省�?user\_country //所在国�?user\_create\_time //关注时间，取消关注后此值为 0
user\_group\_id //分组 ID
user\_in\_blacklist //是否在默名单
user\_head\_img //头像

## web.wxmp 成员列表

### web.wxmp.view

创建微信公众�?REST 客户端�?
请求参数使用普通表单编码（application/x-www-form-urlencoded ）�?
请求参数中的参数值如何是表，则首先转换为 JSON �?
如果请求参数值为函数，则每次请求调用该函数取值�?
所有参数值转换为字符串后并用 URLEncode 编码�?
返回数据如果�?JSON 格式或者表单编码则自动解析为对�?
UrlEncoded 解码 时会自动解析 JSON 字段值（必须是对象或数组�?
如果请求编码也是 JSON ，请改用 web.rest.jsonClient

### web.wxmp.view()

[返回对象:webWxmpViewObject](#webWxmpViewObject)

### web.wxmp.view(/\*指定 web.view 对象\*/)

创建 REST 客户端�?
请求参数使用普通表单编码（application/x-www-form-urlencoded ）�?
请求参数中的参数值如何是表，则首先转换为 JSON�?
如果请求参数值为函数，则每次请求调用该函数取值�?
所有参数值转换为字符串后并用 URLEncode 编码�?
返回数据如果�?JSON 格式或者表单编码则自动解析为对�?
UrlEncoded 解码 时会自动解析 JSON 字段值（必须是对象或数组�?
## webWxmpViewObject 成员列表

### webWxmpViewObject.?

web.rest.client 或继承自 web.rest.client 的对象的其他成员函数或属性�?
请查看相关库函数文档或源�?
### webWxmpViewObject.\_http

inet.http客户端，用于执行http请求

[返回对象:inetHttpObject](#inetHttpObject)

### webWxmpViewObject.addMark

添加备注�?
### webWxmpViewObject.addMark(openId,mark)

添加备注�?
参数 @1 指定用户 openid，可选用参数 @2 指定添加到备注的字符�?�?
### webWxmpViewObject.api

定义API对象，使用成员操作符或下标获取API对象的成员时将会自动转换为新的API对象

### webWxmpViewObject.api("网址模板","HTTP动词","模式�?)

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
### webWxmpViewObject.api("网址模板","HTTP动词","模式�?,HTTP选项)

可选在参数@4�?_INTERNET\_FLAG_ 前缀常量自定义http请求选项

其他参数用法同上

### webWxmpViewObject.api()

[返回对象:webRestApiObject](../rest/client.html#webRestApiObject)

### webWxmpViewObject.cancleBlack(openId)

取消黑名单�?
参数 @openId 指定微信用户 OpenID

### webWxmpViewObject.eachBlackList(分页用户�?分组ID)

```aardio aardio
for userList in eachUserList(20){
    /*遍历获取名单用用户列表，参数 @1 指定每次返回的用户数�?/
}

```

### webWxmpViewObject.eachUserList(分页用户�?分组ID)

```aardio aardio
for userList in eachUserList(20){
    /*遍历获取用户列表，参�?@1 指定每次返回的用户数�?/
}

```

### webWxmpViewObject.getBlackList(选项)

```aardio aardio
webWxmpViewObject.getUserList(
    offset = 0;/*获取黑名单用户列表，可用选项请参考此函数源码�?/
)

```

### webWxmpViewObject.getUserInfo

获取用户信息

### webWxmpViewObject.getUserInfo(openId)

获取并返回用户信息�?
参数 @openId 指定微信用户 OpenID �?
### webWxmpViewObject.getUserList(选项)

```aardio aardio
webWxmpViewObject.getUserList(
    begin_create_time = 1;/*获取用户列表，可用选项请参考此函数源码�?/
)

```

### webWxmpViewObject.lastRequestInfo

最后一次请示使用的所有参数信�?
### webWxmpViewObject.lastRequestMethod

最后一次请示使用的HTTP方法

### webWxmpViewObject.lastRequestUrl

获取最后一次请求的URL

### webWxmpViewObject.lastResponse()

获取最后一次服务器返回的数�?

如果控制台已打开或在开发环境中导入 console 库则在控制台输出数据

下载文件时该值为�?
### webWxmpViewObject.lastResponseContentType

服务器响应头 Content-Type 的�?
### webWxmpViewObject.lastResponseError()

返回服务器最后一次返回的错误响应，并转换为错误对象�?
与调�?API 时转换响应数据一样，支持相同的服务器响应格式 �?
如果错误来自本地（lastStatusCode 属性为 null）则此函数返�?null �?
如果最后一次发生请求成功，则此函数返回 null �?
如果在参�?@1 中指定返回字段，且错误对象包含该字段则使用直接下标获取并返回字段值�?
获取字段失败返回 null 而非抛出异常

### webWxmpViewObject.lastResponseHeaderList("字符串参�?)

获取所有指定字符串作为开始段�?HTTP 头�?
忽略大小写，不忽略冒号以后部分�?
不指定参数则读取全部响应头�?
返回键值对组成的表对象，键名转为小写，每个值都是一个数组�?
如果调用 head, headGet, headPost 等函数�?
或调�?�?API 对象�?head.get,head.post 等函数，

则在请求成功后可调用此函数读�?HTTP �?
### webWxmpViewObject.lastResponseHeaders

获取返回�?HTTP 响应�?
### webWxmpViewObject.lastResponseHeaders("Content-Length:")

获取单个指定�?HTTP 服务器响应头，返回字符串�?
参数指定HTTP头名字或部分名字，忽略大小写，忽略冒号以后部分�?
如果调用 head, headGet, headPost 等函数�?
或调�?�?API 对象�?head.get,head.post 等函数，

则在请求成功后可调用此函数读�?HTTP �?
### webWxmpViewObject.lastResponseHeaders()

获取返回�?HTTP 响应头�?
如果调用 head, headGet, headPost 等函数�?
或调�?�?API 对象�?head.get,head.post 等函数，

则在请求成功后可调用此函数读�?HTTP �?
### webWxmpViewObject.lastResponseString()

获取最后一次服务器返回的原始数据，

请求失败，或者下载文件时此属性值为�?
### webWxmpViewObject.lastStatusCode

获取最近一次请求返回的HTTP状态码

100 ~ 101 为信息提�?
200 ~ 206 表示请求成功

300 ~ 305 表示重定�?
400 ~ 415 表求客户端请求出�?
500 ~ 505 表示服务端错�?
### webWxmpViewObject.lastStatusMessage()

获取最近返回的HTTP状态码文本描述

第二个返回值为状态码

### webWxmpViewObject.messageOnly()

转换为仅处理消息的隐藏窗口，不支持发送消息�?
### webWxmpViewObject.ok()

最后一次请求是否成�?
服务器应答并且状态码�?XX该函数返回真

### webWxmpViewObject.searchComment(key,option)

搜索公众号留言�?
@key 参数指定要搜索的关键字或用户名�?
option 指定接口选项，可省略�?
具体用法请查看函数源码�?
### webWxmpViewObject.sendMessage()

自动发送消息�?
参数 @1 指定用户 openid，可选用参数 @2 指定要发送的字符�?�?
### webWxmpViewObject.show()

显示窗口，参数为 false 隐藏窗口

### webWxmpViewObject.strictParsing

对于 JSON 客户端，如果此属性设�?true�?
且服务器响应头未声明 JSON 类型，返回数据第一个字符不�?{ 也不�?\[�?
则直接返回包含服务器响应数据的字符串�?
此属性值默认为 null

### webWxmpViewObject.userApi

微信用户信息接口�?
[返回对象:webRestApiObject](../rest/client.html#webRestApiObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/wxmp/view.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/wxmp/view.md')

