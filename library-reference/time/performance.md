[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# time.performance 库模块帮助文�?
相关库与函数

time.period, time.timer, time.tick, sleep

## time.performance 成员列表

创建高精度计时器�?
### time.performance.delay()

高精度延时函数�?
参数 @1 指定延时，以毫秒为单位，精度可小�?0.01 毫秒�?
此函数占�?CPU，慎用并避免用于界面线程以避免卡界面且无法处理消息�?
### time.performance.tick()

返回高精度计时�?
以毫秒（ms，千分之一秒）为单位，精度为微秒（us，千分之一毫秒）�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/time/performance.md)

