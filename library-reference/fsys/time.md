[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# fsys.time 库模块帮助文�?
## fsys 成员列表

### fsys.time

�?::FILETIME 兼容的结构体，扩展了更多函数�?
用于存储�?1601�?�?�?开始以 100纳秒 为间隔的数值�?
100纳秒 也就�?0.0001毫秒

创建 ::FILETIME 兼容结构体�?
fsys.time 对象可传�?tostring 转换为文本格式时间，

可转换为文本的时间范围与 time 对象相同�?
fsys.time 对象传入 tonumber 函数返回存储 64 位无符号时间值的浮点数�?
使用 size64 函数可得�?64�?无符号数表示的时间值�?
该时间值为�?1601�?�?�?开始以 100纳秒 为间隔的数�?
### fsys.time()

[返回对象:fsysTimeObject](#fsysTimeObject)

### fsys.time(fileTime,format)

创建 FILETIME 结构

@fileTime 参数可选传入以下类型参数：

1、省略，null 值，注意这不会导致初始化为当前时间�?
2�?:FILETIME 结构体或结构体的部分字段

3、需要复制的 fsys.time 对象

4、普通数值，应为存储 64�?无符号时间值的浮点数�?
5、存储无符号 64 位整数的 math.size64 对象

�?64 位整数表示自 1601�?�?�?开始以 100纳秒 为间隔的时间值�?
可选用 @format 参数指定格式化串，语法与 time 对象相同�?
注意 format 首字符为 "!" 表示存储 UTC 时间�?
默认使用 UTC 时间格式 "!%c"

## fsysTimeObject 成员列表

### fsysTimeObject.copy()

复制对象

### fsysTimeObject.dwHighDateTime

时间值高�?
### fsysTimeObject.dwLowDateTime

时间值低�?
### fsysTimeObject.format

格式化串，语法与 time 对象相同

### fsysTimeObject.fromDosTime(fatDate,fatTime)

DOS 时间格式转换�?FILETIME 格式

如果省略第二个参�?则取第一个参数的高位作为参数�?
### fsysTimeObject.fromSystemTime(time对象)

标准时间对象转换�?FILETIME 对象

省略参数则调�?time.now 函数获取当前时间

[返回对象:fsysTimeObject](#fsysTimeObject)

### fsysTimeObject.local()

UTC 时间转换为本地时�?返回自身

### fsysTimeObject.local(true)

UTC 时间转换为本地时�?

不修改自�?返回本地时间副本

### fsysTimeObject.now()

获取当前时间，返回自身�?
[返回对象:fsysTimeObject](#fsysTimeObject)

### fsysTimeObject.size64()

转换为存储无符号 64 位整数的 math.size64 对象�?
此整数表示自 1601�?�?�?开始以 100纳秒 为间隔的时间�?
### fsysTimeObject.stamp()

以数值类型返�?Unix 时间戳，以毫秒为单位�?
时间�?0 表示 ISO8601 时间 1970-01-01T00:00:00Z

### fsysTimeObject.stamp(true)

以字符串类型返回 Unix 时间戳，以毫秒为单位�?
时间�?0 表示 ISO8601 时间 1970-01-01T00:00:00Z

### fsysTimeObject.toDosTime()

成功返回 dosTime,高位,低位

### fsysTimeObject.toGmtTime()

返回 time.gmt 对象�?
�?RFC1123 格式时间，HTTP 协议使用该格式�?
如果对象的时间值为 null，此函数会返回当前时间�?
[返回对象:timeObject](../time/_.html#timeObject)

### fsysTimeObject.toSystemTime()

返回 time 对象�?
如果对象的时间值为 null，此函数会返回当前时间�?
[返回对象:timeObject](../time/_.html#timeObject)

### fsysTimeObject.utc()

本地时间转换�?UTC 时间,返回自身

### fsysTimeObject.utc(true)

本地时间转换�?UTC 时间,

不修改自�?返回本地时间副本

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/fsys/time.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/fsys/time.md')

