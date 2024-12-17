[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.rest.htmlClient 库模块帮助文�?
## web.rest.htmlClient 成员列表

REST 客户端�?
请求数据，返回数据都使用 string.html 文档对象

创建 REST 客户端�?
请求数据，返回数据都使用 string.html 文档对象

### web.rest.htmlClient.delete()

[返回对象:stringXmlObject](#stringXmlObject)

### web.rest.htmlClient.delete(网址,参数�?

使用该DELETE方法提交请求,删除资源

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### web.rest.htmlClient.get()

[返回对象:stringXmlObject](#stringXmlObject)

### web.rest.htmlClient.get(网址,参数�?

使用该GET方法提交请求,获取资源

请求参数将会自动转换为URL附加参数,

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### web.rest.htmlClient.patch()

[返回对象:stringXmlObject](#stringXmlObject)

### web.rest.htmlClient.patch(网址,参数�?

使用该PATCH方法提交请求,更新资源

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### web.rest.htmlClient.post()

[返回对象:stringXmlObject](#stringXmlObject)

### web.rest.htmlClient.post(网址,参数�?

使用该POST方法提交请求,新增或修改资�?
请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

### web.rest.htmlClient.put()

[返回对象:stringXmlObject](#stringXmlObject)

### web.rest.htmlClient.put(网址,参数�?

使用该PUT方法提交请求,替换或更新资�?
请求参数可以指定表或字符�?如果是表请求前会转换为字符串

成功返回数据,失败返回空�?错误信息,错误代码

## web.rest 成员列表

### web.rest.htmlClient("UserAgent","代理服务�?,"绕过代理的主�?,连接选项)

创建 REST 客户端，所有参数可选�?
UserAgent 用于自定�?User-Agent 请求标头，用于服务器识别请求程序特征�?
HTTP 代理服务器请指定�?"代理服务器地址:端口" 格式�?
SOCKS 代理服务器请指定�?"socks=代理服务器地址:端口" 格式

└── [代理格式说明](../../../library-guide/std/inet/proxy.html)

"绕过代理的主�? 用法参�?inet.setProxy 源码的示例，一般不需要指定�?
连接选项可用一个数值参数指定打开会话的选项，一般不需要指定�?
### web.rest.htmlClient()

[返回对象:webRestClientObject](client.html#webRestClientObject)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/rest/htmlClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/rest/htmlClient.md')

