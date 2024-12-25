[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# debug.log 库模块帮助文�?
## debug.log 成员列表

调试日志文件操作

所有输出函数在开发时同时输出到控制台

发布后自动使用BASE64编码后写入日�?
### debug.log.checkSize(0x20000)

检测日志文件是否超�?28KB,

超过参数指定的大小则清空日志文件

### debug.log.decode

解码并在控制台输出日志文件内�?
### debug.log.dump()

写入调试日志一个以上的参数

其中table类型将序列化为字符串

### debug.log.dumpJson()

写入调试日志的参数转换为JSON然后输出

### debug.log.print("字符串参�?)

写入调试日志一个以上的参数

### debug.log.printf("字符串参�?)

将所有参数调用string.format格式化然后输�?
### debug.log.setPath("/config/dbg$.log")

设志日志文件路径,进程内全局有效,

如果不指定路�?默认设置�?/config/dbg$.log

### debug.log.traceback()

在控制台输出当前函数调用栈信�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/debug/log.md)

