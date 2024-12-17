[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# process.rpc.jsonClient 库模块帮助文�?
## process.rpc 成员列表

### process.rpc.jsonClient

基于进程管道通过读写进程标准输入输出实现�?JSON-RPC 客户端�?
用法参考『范�?/ 调用其他语言 / Go / RPC』，�?process.r 扩展库范例�?
规则说明�?
1�?所�?JSON-RPC 消息必须置于 { } �?\[ \] 内，aardio 输出 JSON 时以换行符结束�?
2�?
aardio 读取进程输出时获取第一个能成功解析为响应对象的 JSON�?
└── 单次调用的响应对象应当是 { } 包含的对象且包含 id 字段�?
└── 批量调用的响应对象应当是 \[ \] 包含的非空数组且数组元素存在 id 字段�?
响应对象 JSON 不要求以换行符结束，忽略进程的其他输出�?
客户端总是在发送请求后再读取回复（应答对象�?id 字段必须与请求对象的 id 字段相同）�?
关于 [JSON-RPC 2.0](javascript:if(confirm('http://www.jsonrpc.org/specification  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='http://www.jsonrpc.org/specification')

创建 JSON-RPC 2.0 客户端，兼容 JSON-RPC 1.0 �?
用法请参考『范�?/ 调用其他语言 / Go / RPC』，

�?process.r 扩展库范�?
启动失败返回 null,错误信息�?
成功返回 RPC 调用对象

### process.rpc.jsonClient()

[返回对象:processRpcJsonClientObject](#processRpcJsonClientObject)

### process.rpc.jsonClient(执行文件,命令行参�?STARTUPINFO)

启动目标进程，并返回 JSON-RPC 客户端�?
目标进程自动绑定作业对象 process.job.limitKill �?
进程管道默认编码设为 UTF-8�?
命令行参数可以是一个数组、一个或多个字符串参�?

数组或多个命令行参数调用 process.joinArguments 合并,

不在双引号内、且包含空白或需要转义的参数转义处理后首尾添加双引号

注意：如果参�?@1 为字符串�?
每次 RPC 调用时就会自动检测并重启意外退出的 RPC 服务进程�?
但每次调用只会尝试重启一次，不会连续重启

### process.rpc.jsonClient(进程管道)

创建 JSON-RPC 客户端�?
参数 @1 必须指定 process.popen 对象

启动失败返回 null,错误信息�?
成功返回 RPC 调用对象

## processRpcJsonClientObject 成员列表

### processRpcJsonClientObject.?

远程对象名或远程方法名字�?
远程函数调用成功则第一个返回值为表对象，

└── 该对象的 result 字段为返回值，error 为错误对象，两个字段不会同时存在�?
└── error 对象�?message 为错误信息，code 为错误代码，data 为错误附加数据�?
└── 如果存在 error 对象，则�?2 个返回值为 error 对象�?JSON 文本格式�?
调用失败第一个返回值为 null ，第二个返回值为错误信息

如果调用 rpc.beginTrans 函数开始一个批量调用，

则返回一个可以指�?end 成员函数的对象，服务器应答时自动回调�?end 函数

[返回对象:processRpcJsonClientObject](#processRpcJsonClientObject)

## processRpcJsonClientObject.rpc 成员列表

RPC 本地客户端对�?
所以本地函数放在这个对象里�?
用户不得添加、删除、修改此对象的任何成�?
### processRpcJsonClientObject.rpc.afterJsonStringify

```aardio aardio
processRpcJsonClientObject.rpc.afterJsonStringify = function(jsonData){
    /*可以在这里加密客户端JSON，返�?null 中止本次调用�?/
    return jsonData;
}

```

### processRpcJsonClientObject.rpc.beforeJsonParse

```aardio aardio
processRpcJsonClientObject.rpc.beforeJsonParse = function(jsonData){
    /*可以在这里解密服务端数据，返�?null 中止本次调用�?定义此函数以后，服务端每次输出的 JSON 必须以换行符结束*/
    return jsonData;
}

```

### processRpcJsonClientObject.rpc.beforeRequest(请求数据)

```aardio aardio
processRpcJsonClientObject.rpc.beforeRequest = function(reqData){
    /*此回调事件在发送请求前触发�?reqData.params 是即将发送的参数�?/
    return reqData;
}

```

### processRpcJsonClientObject.rpc.beginTrans()

开始批量调用，注意多数服务器并不支持批量调用�?
aardio 实现�?process.rpc.jsonServer 可支持批量调用�?
批量调用时单次调用的返回值是一个表

可对返回值指�?end 成员函数�?
end 函数会在 commitTrans 提交批量调用成功后被触发

### processRpcJsonClientObject.rpc.charset

获取或修改编�?此值必须为大写，默认为"UTF-8",

因为 JSON 规定�?Unicode 编码方案,所以不建议也不应该修改这个�?
### processRpcJsonClientObject.rpc.close()

关闭客户�?
### processRpcJsonClientObject.rpc.commitTrans()

完成批量调用，注意多数服务器并不支持批量调用�?
aardio 实现�?process.rpc.jsonServer 可支持批量调用�?
### processRpcJsonClientObject.rpc.ctrlEvent(0)

发�?Ctrl+C（SIGINT信号�?
信号将传递到与目标进程控制台连接的所有非分离控制台进�?
64位目标进程会导致当前控制台暂时关�?
### processRpcJsonClientObject.rpc.ctrlEvent(1)

发�?Ctrl+Break（SIGINT信号�?
信号将传递到与目标进程控制台连接的所有非分离控制台进�?
64位目标进程会导致当前控制台暂时关�?
### processRpcJsonClientObject.rpc.getExitCode()

该函数调用成功有两个返回�?目标进程退出代�?目标进程是否已退�?
### processRpcJsonClientObject.rpc.kwargs

是否支持 Python 命名参数（kwargs ）�?
仅适用�?process.python.jsonRpc，仅 varargs 属性为 true 时有效�?
调用时命名参数必须写在参数列表最前面�?
其后第一个出现的位置参数对应服务端的第一个位置参�?
### processRpcJsonClientObject.rpc.lastResponse()

获取最后一次服务器返回的原始数�?

如果控制台已打开或在开发环境中导入 console 库则在控制台输出数据

下载文件时该值为�?
### processRpcJsonClientObject.rpc.notify("函数�?,参数)

发送通知,服务器不返回�?

如果 varargs 属性指定为 true 时将不定个数参数合为数组�?
varargs�?false 时直接发送参�?
成功返回 true，失败返�?null,错误信息

### processRpcJsonClientObject.rpc.onError

```aardio aardio
processRpcJsonClientObject.rpc.onError = function(message){
    /*目标进程存在标准库错误输出时触发此函�?/
}

```

### processRpcJsonClientObject.rpc.process

进程管道对象

[返回对象:processPopenObject](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html#processPopenObject')

### processRpcJsonClientObject.rpc.resume()

目标进程恢复运行

### processRpcJsonClientObject.rpc.rollbackTrans()

撤消尚未提交的批量调�?
### processRpcJsonClientObject.rpc.stillActive()

目标进程是否仍然运行

### processRpcJsonClientObject.rpc.suspend()

目标进程暂停运行

### processRpcJsonClientObject.rpc.terminate()

强制关闭进程并释放目标进程对象�?
注意如果在构造函数中指定了执行文件路径�?
且在目标进程退出后继续调用 RPC 函数�?
则会自动重启 RPC 服务进程�?
### processRpcJsonClientObject.rpc.varargs

默认值为 true,

值为 true 时将不定个数的参数放入数组发送给服务�?
值为 false 时直接将单个参数发送给服务�?
JSON-RPC 2.0 一个会制造混乱的地方�?
如果params是一个数组，并没有规定是展开为一个参数，还是作为一个数组参数�?
目前 aardio �?RPC 服务端会负责展开数组作为多个参数�?
但客户端需要在这里手动设置

### processRpcJsonClientObject.rpc.version

值为 JSON-RPC 协议版本�?2.0"

不应该修改这个�?
### processRpcJsonClientObject.rpc.wait()

等待目标进程关闭,可选使用一个毫秒值参数设定超时�?
超时或失败返�?null，进程退出则返回�?为true�?
返回�?为标准输出，返回�?为错误输出，返回�?为退出代�?
如被调用进程写满输出缓冲区，而调用进程没有读取，

则被调用进程会一直等待，此函数将无法返回�?
改用 readAll 函数读取输入可避免该问题�?
### processRpcJsonClientObject.rpc.waitOne()

等待目标进程关闭，不会阻塞当前线程窗口消息�?
可用一个毫秒值参数设定超时�?
超时或失败返�?null，进程已退出则返回�?为true�?
返回�?为标准输�?返回�?为错误输�?返回�?为退出代�?
如果被调用进程写满输出缓冲区，而调用进程没有读取，

则被调用进程会一直等待，此函数将无法返回�?
改用 readAll 函数读取输入可避免该问题�?
注意如果正在调用异步 logResponse 回显到窗口对象�?
�?waitOne 函数仅返回单个值，不读取任何输�?
### processRpcJsonClientObject.rpc.xcall("函数�?,参数)

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

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/rpc/jsonClient.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/rpc/jsonClient.md')

