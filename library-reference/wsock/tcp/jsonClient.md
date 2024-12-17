[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# wsock.tcp.jsonClient 库模块帮助文�?
## wsock.tcp 成员列表

### wsock.tcp.jsonClient

JSON-RPC 2.0 客户�?
aardio 输出的请�?JSON 不包含换行并以换行符'

'结束�?
服务器应�?JSON 对象�?id 字段必须与请�?id 一致，

在批量请求时应答数组应当包含 id 一致的对象（不需要返回空数组�?
[关于 JSON-RPC 2.0](javascript:if(confirm('http://www.jsonrpc.org/specification  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='http://www.jsonrpc.org/specification')

### wsock.tcp.jsonClient()

[返回对象:wsockRpcJsonClientObject](#wsockRpcJsonClientObject)

### wsock.tcp.jsonClient(主机,端口)

创建REST客户�?
也可以在第一个参数中使用冒号分隔主机与端�?
## wsockRpcJsonClientObject 成员列表

### wsockRpcJsonClientObject.?

远程对象名或远程方法名字�?
远程函数调用成功则第一个返回值为表对象，

└── 该对象的 result 字段为返回值，error 为错误对象，两个字段不会同时存在�?
└── error 对象�?message 为错误信息，code 为错误代码，data 为错误附加数据�?
└── 如果存在 error 对象，则�?2 个返回值为 error 对象�?JSON 文本格式�?
调用失败第一个返回值为 null ，第二个返回值为错误信息

如果调用 rpc.beginTrans 函数开始一个批量调用，

则返回一个可以指�?end 成员函数的对象，服务器应答时自动回调�?end 函数

[返回对象:wsockRpcJsonClientObject](#wsockRpcJsonClientObject)

### wsockRpcJsonClientObject.process

如果使用 process.rpc.tcpJsonClient 创建对象�?
则此属性为 process.popen 对象，否则为空�?
[返回对象:processPopenObject](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html#processPopenObject')

## wsockRpcJsonClientObject.rpc 成员列表

RPC本地客户端对�?
所以本地函数放在这个对象里�?
用户不得添加、删除、修改此对象的任何成�?
### wsockRpcJsonClientObject.rpc.beforeRequest(请求数据)

```aardio aardio
wsockRpcJsonClientObject.rpc.beforeRequest = function(reqData){
    /*此回调事件在发送请求前触发
reqData.params是即将发送的参数*/
    return reqData;
}

```

### wsockRpcJsonClientObject.rpc.beginTrans()

开始批量调�?
批量调用时单次调用的返回值是一个表

可对返回值指定end成员函数�?
end函数会在commitTrans提交批量调用成功后被触发

### wsockRpcJsonClientObject.rpc.charset

获取或修改编�?默认�?UTF-8",

因为 JSON 规定�?Unicode 编码方案，所以不建议也不应该修改这个�?
如果指定为除"UTF-8"之外的值，则按本机默认代码页转换服务端编码

### wsockRpcJsonClientObject.rpc.client

用于执行请求�?wsock.tcp.client 对象

[返回对象:tcpclientObject](client.html#tcpclientObject)

### wsockRpcJsonClientObject.rpc.close()

关闭RPC客户端并释放资源

### wsockRpcJsonClientObject.rpc.commitTrans()

完成批量调用

### wsockRpcJsonClientObject.rpc.lastResponse()

获取最后一次服务器返回的原始数�?

如果控制台已打开或在开发环境中导入console库则在控制台输出数据

下载文件时该值为�?
### wsockRpcJsonClientObject.rpc.lastStatusCode

获取最近一次请求返回的HTTP状态码

100 ~ 101 为信息提�?
200 ~ 206 表示请求成功

300 ~ 305 表示重定�?
400 ~ 415 表求客户端请求出�?
500 ~ 505 表示服务端错�?
### wsockRpcJsonClientObject.rpc.lastStatusMessage()

获取最近返回的HTTP状态码文本描述

第二个返回值为状态码

### wsockRpcJsonClientObject.rpc.notify("函数�?,参数)

发送通知,服务器不返回�?

如果 varargs 属性指定为 true 时将不定个数参数合为数组�?
varargs �?false 时直接发送参�?
成功返回 true，失败返�?null,错误信息

### wsockRpcJsonClientObject.rpc.rollbackTrans()

撤消尚未提交的批量调�?
### wsockRpcJsonClientObject.rpc.setAuth("用户�?,"密码")

设置HTTP登录用户�?密码

### wsockRpcJsonClientObject.rpc.varargs

默认值为 true,

值为 true 时将不定个数的参数放入数组发送给服务�?
值为false时直接将单个参数发送给服务�?
JSON-RPC 2.0 一个会制造混乱的地方�?
如果 params 是一个数组，并没有规定是展开为一个参数，还是作为一个数组参数�?
目前aardio的RPC服务端会负责展开数组作为多个参数�?
但客户端需要在这里手动设置

### wsockRpcJsonClientObject.rpc.version

值为 JSON-RPC 协议版本�?2.0"

不应该修改这个�?
### wsockRpcJsonClientObject.rpc.xcall("函数�?,参数)

调用远程函数�?
如果 varargs 属性指定为 true 时将不定个数参数合为数组�?
varargs �?false 时直接发送参�?
远程函数调用成功则第一个返回值为表对象，

└── 该对象的 result 字段为返回值，error 为错误对象，两个字段不会同时存在�?
└── error 对象�?message 为错误信息，code 为错误代码，data 为错误附加数据�?
└── 如果存在 error 对象，则�?2 个返回值为 error 对象�?JSON 文本格式�?
调用失败第一个返回值为 null ，第二个返回值为错误信息

如果调用 rpc.beginTrans 函数开始一个批量调用，

则返回一个可以指�?end 成员函数的对象，服务器应答时自动回调�?end 函数

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/jsonClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/wsock/tcp/jsonClient.md')

