[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.timer 库模块帮助文�?
## win 成员列表

### win.timer

定时管理�?
### win.timer()

[返回对象:winTimerObject](#winTimerObject)

### win.timer(winform,interval)

创建定时�?
如果不指定窗体对�?则创建消息窗�?
interval为可选参数，用于指定间隔时间,以毫秒为单位,默认�?00毫秒

## winTimerObject 成员列表

### winTimerObject.disable()

禁用定时�?
### winTimerObject.enable(interval,count)

启用定时�?

可选使用interval参数中指定间隔时�?以毫秒为单位,

可选使用count参数限定定时器执行次�?

如果指定了有效执行次�?则定时器会立即执行一次onTimer函数,

否则会先延时再执行onTimer函数

### winTimerObject.getInterval()

读取定时器间隔时�?
### winTimerObject.onEnd

```aardio aardio
winTimerObject.onEnd = function(){
    /*定时器停止时触发此事�?/
}

```

### winTimerObject.onTimer

```aardio aardio
winTimerObject.onTimer = function(){
    /*设置定时器触发函�?此函数不应返回任何�?/
}

```

### winTimerObject.setInterval(1)

修改定时器间隔时�?

以毫秒为单位

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/timer.md)

