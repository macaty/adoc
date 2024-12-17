[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# dotNet.ps 库模块帮助文�?
## dotNet 成员列表

### dotNet.ps(script,parameters,useLocalScope)

执行PowerShell脚本，返回输出字符串�?
@script 参数指定PowerShell脚本或脚本路径，

可选用@parameters参数指定一个表，包含调用参数名值对�?
@parameters参数既可以包含名值对，也可以包含仅指定参数名的数组，

表里的参数名不需要加 $�?\- 前缀，PowerShell里要�?前缀�?
参数值可以使用任�?.Net 支持的数据类型，

如果 @parameters 是字符串，则后面可以添加任意个数字符串参数，

@useLocalScope 为可选参数，@parameters 为字符串时无 @useLocalScope 参数

PowerShell 脚本�?param 接收命名参数,

�?args 接收匿名参数

## dotNet.ps 成员列表

支持 Windows PowerShell 2.0 以上�?
Win7 自带 PowerShell 2.0，可回调 dotNet.ps.export 导出�?aardio 参数对象�?
Win10/Win11 自带 PowerShell 5.1，已支持直接回调 aardio 参数对象�?
### dotNet.ps.command(command,parameters,useLocalScope)

执行 PowerShell 命令�?
成功返回输出字符�?失败返回null,错误信息�?
可选用@parameters参数指定一个表，包含调用参数名值对�?
@parameters参数既可以包含名值对，也可以包含仅指定参数名的数组，

表里的参数名不需要加 $�?\- 前缀�?
参数值可以使用任�?.Net 支持的数据类型，

如果 @parameters 是字符串，则后面可以添加任意个数字符串参数，

@useLocalScope 为可选参数，@parameters 为字符串时无 @useLocalScope 参数

### dotNet.ps.export()

将参�?@1 指定�?aardio 表对象转换为 PowerShell 参数对象

�?PowerShell 中可使用 InvokeMember 调用成员函数，参数@1为成员函数名�?
也可以使用下标读写对象属性值�?
Win10/Win11 自带 PowerShell 5.1 已经直接支持回调 aardio 对象�?
如果不需要兼容旧�?PowerShell 则不需要使用此函数

### dotNet.ps.json(ps,parameters,useLocalScope)

```aardio aardio
dotNet.ps.json(`ConvertTo-Json /*执行 PowerShell 脚本，所有参数与 dotNet.ps 相同�?ConvertTo-Json 兼容�?PowerShell 2.0�?返回文本作为 JSON 自动解析�?aardio 对象*/`)

```

### dotNet.ps.onWrite

```aardio aardio
dotNet.ps.onWrite = function(str){
    /*PowerShell 输出文本回调此函数，
参数 @str 为待输出的字符串*/
}

```

### dotNet.ps.onWriteProgress

```aardio aardio
dotNet.ps.onWriteProgress = function(sourceId,record){
    /*PowerShell 进度条回调此函数�?参数 record.Activity 为任务标题，
参数 record.StatusDescription 为进度描述，
参数 record.PercentComplete 为进度百分比�?PowerShell 回调出错不会抛出异常�?如果有需要在函数内部自行 try catch 捕获代码错误*/
    winform.plus.text = record.StatusDescription;
    winform.plus.progressPercentage = record.PercentComplete;
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/dotNet/ps.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/dotNet/ps.md')

