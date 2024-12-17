[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.rest.jsonLiteClient 库模块帮助文�?
## 全局对象 成员列表

### web.rest..jsonLiteClient

创建 REST 客户端�?
请求参数使用普通表单编码（application/x-www-form-urlencoded ）�?
请求参数中的参数值如果是表，则首先转换为 JSON �?
如果请求参数值为函数，则每次请求调用该函数取值�?
所有参数值转换为字符串后并用 URLEncode 编码�?
返回数据如果�?JSON 格式或者表单编码则自动解析为对�?
UrlEncoded 解码 时会自动解析 JSON 字段值（必须是对象或数组�?
如果请求编码也是 JSON ，请改用 web.rest.jsonClient

## web.rest 成员列表

### web.rest.jsonLiteClient

REST 客户端�?
请求参数使用普通表单编码（application/x-www-form-urlencoded ）�?
请求参数中的参数值如果是表，则首先转换为 JSON �?
如果请求参数值为函数，则每次请求调用该函数取值�?
所有参数值转换为字符串后并用 URLEncode 编码�?
返回数据如果�?JSON 格式或者表单编码则自动解析为对�?
UrlEncoded 解码 时会自动解析 JSON 字段值（必须是对象或数组�?
如果请求编码也是 JSON ，请改用 web.rest.jsonClient

### web.rest.jsonLiteClient("UserAgent","代理服务�?,"绕过代理的主�?,连接选项)

创建 REST 客户端，所有参数可选�?
UserAgent 用于自定�?User-Agent 请求标头，用于服务器识别请求程序特征�?
HTTP 代理服务器请指定�?"代理服务器地址:端口" 格式�?
SOCKS 代理服务器请指定�?"socks=代理服务器地址:端口" 格式

└── [代理格式说明](../../../library-guide/std/inet/proxy.html)

"绕过代理的主�? 用法参�?inet.setProxy 源码的示例，一般不需要指定�?
连接选项可用一个数值参数指定打开会话的选项，一般不需要指定�?
### web.rest.jsonLiteClient()

[返回对象:webRestClientObject](client.html#webRestClientObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/rest/jsonLiteClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/rest/jsonLiteClient.md')

