[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.taskScheduler 库模块帮助文�?
## win 成员列表

### win.taskScheduler

计划任务

### win.taskScheduler()

[返回对象:winTaskSchedulerObject](#winTaskSchedulerObject)

### win.taskScheduler(窗体对象)

参数可省�?
注意仅在线程启动消息循环后起作用

执行计划任务会阻塞定时器直到任务执行完成

不希望阻塞定时器可使�?winform.setTimeout、或多线程异步执行代�?
## winTaskSchedulerObject 成员列表

### winTaskSchedulerObject.create("名字",执行函数)

```aardio aardio
winTaskSchedulerObject.create("计划任务名字",function( arguments ){

} , /*其他调用任务的参�?/ )

```

### winTaskSchedulerObject.create()

[返回对象:winTaskSchedulerTaskObject](#winTaskSchedulerTaskObject)

### winTaskSchedulerObject.delete("任务名字")

删除指定任务

### winTaskSchedulerObject.deserialize

反序列化计划任务

### winTaskSchedulerObject.deserialize(字符�?默认回调函数)

反序列化计划任务,并指定默认回调函�?
### winTaskSchedulerObject.get("任务名字")

读取指定任务

### winTaskSchedulerObject.get()

[返回对象:winTaskSchedulerTaskObject](#winTaskSchedulerTaskObject)

### winTaskSchedulerObject.serialize()

序列化计划任务配置并返回字符�?
### winTaskSchedulerObject.set("任务名字",执行函数)

修改任务执行函数

### winTaskSchedulerObject.start(任务检测间�?

开始运行计划任�?
注意仅在线程启动消息循环后起作用

检测间隔参数可�?默认�?000毫秒

执行计划任务会阻塞定时器直到任务执行完成

如果在计划任务中执行了win.delay等继续消息循环的代码�?
在计划任务退出前不会再触发同一计划任务（重入）�?
不希望阻塞定时器可使�?winform.setTimeout、或多线程异步执行代�?
### winTaskSchedulerObject.stop()

停止计划任务

## winTaskSchedulerTaskObject 成员列表

### winTaskSchedulerTaskObject.beginTime

开始时�?
该值默认为�?
### winTaskSchedulerTaskObject.enabled

是否允许执行

### winTaskSchedulerTaskObject.expirationTime

结束时间

该值默认为�?
### winTaskSchedulerTaskObject.interval

```aardio aardio
winTaskSchedulerTaskObject.interval = {
    second = 间隔秒数 /*请指定间隔执行的时间字段�?/;
    minute = 间隔分钟�?;
    hour = 间隔小时�?;
    day = 间隔天数 ;
    month = 间隔月数 ;
}

```

### winTaskSchedulerTaskObject.lastResult

最后一次执行的返回�?
### winTaskSchedulerTaskObject.lastRunTime

任务最后运行的时间

### winTaskSchedulerTaskObject.pending

任务是否在等待状�?
如果正在执行任务，此属性返回false

### winTaskSchedulerTaskObject.time

```aardio aardio
winTaskSchedulerTaskObject.time = {
    second =  �?/*请指定准时启动任务的时间字段�?
可以指定数�?也可以用数组指定多个�?
不作为条件匹配的时间字段不用指定
即使任务在启动时间内完成也不会重新启动任�?/;
    minute = 分钟 ;
    hour = 小时 ;
    day = �?;
    month = �?;
    dayofweek = {1,2,3,4,5,6,0}
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/taskScheduler.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/taskScheduler.md')

