[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# time.zone 库模块帮助文�?
## time.zone 成员列表

### time.zone.getInfo()

返回当前时区信息

[返回对象:timeZoneInfoObject](#timeZoneInfoObject)

### time.zone.setInfo(zoneInfo)

```aardio aardio
time.zone.setInfo( bias = -480 )

```

### time.zone.toLocal()

[返回对象:timeObject](_.html#timeObject)

### time.zone.toLocal(时间对象,时差)

参数一为time对象,

时差以分钟为单位,默认取当前时区时�?
应用ISO 8601格式

### time.zone.toUtc()

[返回对象:timeObject](_.html#timeObject)

### time.zone.toUtc(时间对象,时差)

参数一为time对象,

时差以分钟为单位,默认取当前时区时�?
应用ISO 8601格式

## timeZoneInfoObject. 成员列表

### timeZoneInfoObject..bias

时差

### timeZoneInfoObject..daylightBias

夏令时差

### timeZoneInfoObject..daylightDate

夏令�?
[返回对象:timeObject](_.html#timeObject)

### timeZoneInfoObject..daylightName

夏令时区�?
### timeZoneInfoObject..formatBias()

格式化如�?08:00

### timeZoneInfoObject..now()

当前时间

[返回对象:timeObject](_.html#timeObject)

### timeZoneInfoObject..standardBias

标准时差

### timeZoneInfoObject..standardDate

当前时间

[返回对象:timeObject](_.html#timeObject)

### timeZoneInfoObject..standardName

时区�?
### timeZoneInfoObject..toLocal()

[返回对象:timeObject](_.html#timeObject)

### timeZoneInfoObject..toLocal(时间对象)

UTC时间转换为区域时�?
省略参数则使用当前时�?
应用ISO 8601格式

### timeZoneInfoObject..toUtc()

[返回对象:timeObject](_.html#timeObject)

### timeZoneInfoObject..toUtc(时间对象)

区域时间转换为UTC时间

省略参数则使用当前时�?
应用ISO 8601格式

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/time/zone.md)

