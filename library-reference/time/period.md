[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# time.period 库模块帮助文�?
相关库与函数

time.performance, time.timer, time.tick, sleep

## time 成员列表

### time.period

修改 sleep 函数精度�?
Win10 2004 以前会影响系统全局设置�?
Win11 开始如果拥有窗口的进程最小化或不可见，则不保证设置的精度有效�?
关于此功能的注意事项，请查看系统 API timeBeginPeriod 的文档�?
[https://learn.microsoft.com/zh-cn/windows/win32/api/timeapi/nf-timeapi-timebeginperiod](https://learn.microsoft.com/zh-cn/windows/win32/api/timeapi/nf-timeapi-timebeginperiod)

### time.period(精度,调用函数,其他调用参数)

执行调用函数，并在执行期间修改系统定时器精度�?
精度参数以毫秒为单位�?
如果需要使�?time.period �?
请调�?sleep 而非可能指向 win.delay �?thread.delay 函数�?
此函数主要影�?sleep 函数，对 win.delay 函数作用不大�?
应避免在界面线程使用 time.period �?sleep 函数，以防止卡界面无法处理消息�?
如果需要高精度计时，请使用 time.performance.tick 函数�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/time/period.md)

