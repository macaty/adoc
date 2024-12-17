[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.http 库模块帮助文�?
## string 成员列表

### string.http(header,body)

header 可以是指定请求头名值对的表�?
也可以是任何 web.joinHeaders 兼容的表或数组�?
body 可以是任何数据�?
如果 body 是一个表则转换为 JSON �?
如果未指定请求头 Content-Type�?
则同时修改其值为 "application/json; charset=utf-8"

可选在第一个参数前面添加一个字符串参数以加�?HTTP 请求头之前�?
如果有更多参数，则不转换 JSON 且全部转为字符串拼接�?
拼接分隔符为 '\\r

'，header �?body 间则�?'\\r

\\r

'

## string.http 成员列表

用于构建�?HTTP 请求消息，并解析�?HTTP 应答消息�?
目前应用�?web.edgeTextToSpeech 库�?
构建�?HTTP 请求消息

### string.http.parse()

�?HTTP 协议兼容规则解析响应消息�?
参数支持字符串或 buffer�?
HTTP 头解析为表对象，头名字转为小写�?
body 作为第二个返回值�?
如果 header �?body 间只用了单个 '\\r

' 分隔�?
则最后一行转换为 body 返回

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/http.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/http.md')

