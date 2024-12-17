[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# time.ole 库模块帮助文�?
## time 成员列表

### time.isole()

检测参数中指定的值是否time.ole对象

### time.ole()

[返回对象:timeOleObject](#timeOleObject)

### time.ole(,"%Y/%m/%d %H:%M:%S")

创建OLE时间对象，返回对象可传入其他线程使用�?
参数@1可以是表示时间的数值、字符串、或time,time.ole 对象,

也可以指定一个仅提供time对象的部分键值的表作为参�?
参数@2指定格式化串,首字符为!表示GMT时间

可选使用@3指定对象的locale属�?即文本格式化语言,

locale支持的参数与setlocale相同,英文"enu",中文"chs"

此对象继承自时间对象,所有功能相�?与time对象的区别是:

OLE时间对象在输入数值或转换为数值是是以天数为单位的,而time对象以秒为单�?

OLE时间对象支持�?00�?�?日到9999�?2�?1日的时间,正数1899�?2�?0日算起的天数,

小数部分是一天当中的片段时间,负数表示1899�?2�?0日之前的时间.

注意：格式化为字符串时调用systemFormat格式�?请参考该函数说明

## time.ole 成员列表

数值运算支持从100�?�?日到9999�?2�?1日的时间

正数1899�?2�?0日算起的天数，小数部分是一天当中的片段时间

负数表示1899�?2�?0日之前的时间

注意：格式化为字符串时调用systemFormat格式�?请参考该函数说明

### time.ole.now()

[返回对象:timeOleObject](#timeOleObject)

## timeOleObject 成员列表

### timeOleObject.addday()

[返回对象:timeOleObject](#timeOleObject)

### timeOleObject.addday(输入数�?

增加天数,可以为负�?返回自身

### timeOleObject.addhour()

[返回对象:timeOleObject](#timeOleObject)

### timeOleObject.addhour(输入数�?

增加小时�?可以为负�?返回自身

### timeOleObject.addminute()

[返回对象:timeOleObject](#timeOleObject)

### timeOleObject.addminute(输入数�?

增加分钟�?可以为负�?返回自身

### timeOleObject.addmonth()

[返回对象:timeOleObject](#timeOleObject)

### timeOleObject.addmonth(输入数�?

增加月份�?返回自身

### timeOleObject.addsecond()

[返回对象:timeOleObject](#timeOleObject)

### timeOleObject.addsecond(输入数�?

增加秒数,可以为负�?返回自身

### timeOleObject.day

�?
### timeOleObject.dayofweek

星期

星期一到星期六的值对应数值为1�?,星期日的值为 0,

注意修改这个字段不会更新时间�?

这个字段只有参与数值运算或调用 add\*\*\* 函数才会填充或更�?

例如调用 addday(0) 会更新此字段

### timeOleObject.diffday(指定datetime对象)

计算两个time对象相差天数

### timeOleObject.diffhour(指定datetime对象)

计算两个time对象相差小时�?
### timeOleObject.diffminute(指定datetime对象)

计算两个time对象相差分钟�?
### timeOleObject.diffmonth(指定datetime对象)

计算两个time对象相差月份

### timeOleObject.diffsecond(指定datetime对象)

计算两个time对象相差秒数

### timeOleObject.endstr

文本解析为时间后�?
最后一个格式化标记解析成功并跳过空白字符以后的剩余的连续不含空白字符串�?
可用于后续解析iso8601等格式的时区（解析后将必须删除）�?
### timeOleObject.format

```aardio aardio
timeOleObject.format="%Y�?m�?d�?%H�?M�?S�?;
//指定格式化串,首字符为!表示GMT时间

```

### timeOleObject.hour

小时

### timeOleObject.local()

将UTC时间转换为本地时�?
格式化串首字符为!表示UTF时间

如果不是UTC时间直接返回

返回自身

### timeOleObject.local(true)

将UTC时间转换为本地时�?
并创建一个新的时间对象返�?
如果不是UTC时间直接复制并返�?
不修改自身并返回新对�?
### timeOleObject.locale

格式化时间使用的语言代码

参数与setlocale相同,英文"enu",中文"chs",

该属性为空表示使用当前默认语言

### timeOleObject.milliseconds

毫秒

### timeOleObject.minute

分钟

### timeOleObject.month

�?
### timeOleObject.second

�?
### timeOleObject.systemFormat(格式化串,区域代码)

使用系统格式化规则格式化时期,区域代码应使�?字母缩写

不指定格式化串时获取format属性并转为系统时间格式化串,

转换规则如下�?
"%y" -> "yy" 表示2位年�?
"%Y" -> "yyyy" 表示4位年�?
"%B" -> "MMMM" "" 表示月份全称

"%b" -> "MMM" 表示月份缩写

"%m" -> "MM" 表示2位月�?
"%d" -> "dd" 表示月份的第几天

"%H" -> "HH" 表示2�?4时制小时

"%I" -> "hh" 表示2�?2时制小时

"%M" -> "mm" 表示2位分钟数

"%S" -> "ss" 表示2分秒�?
"%p" -> "tt" 表示12时制显示上午或下�?
### timeOleObject.toSystemFormat()

取参数指定的格式化串，或format属性指定的格式化串,

转换为系统格式化语法并返回新的格式化串，不会修改原来的格式化�?

转换规则如下�?
"%y" -> "yy" 表示2位年�?
"%Y" -> "yyyy" 表示4位年�?
"%B" -> "MMMM" "" 表示月份全称

"%b" -> "MMM" 表示月份缩写

"%m" -> "MM" 表示2位月�?
"%d" -> "dd" 表示月份的第几天

"%H" -> "HH" 表示2�?4时制小时

"%I" -> "hh" 表示2�?2时制小时

"%M" -> "mm" 表示2位分钟数

"%S" -> "ss" 表示2分秒�?
"%p" -> "tt" 表示12时制显示上午或下�?
注意不要直接修改format属性为系统格式化语�?
这会导致time.ole与time对象不能兼容转换

### timeOleObject.update()

重新计算时间并更新dayOfWeek字段.

### timeOleObject.utc()

将本地时间转换为UTC时间

格式化串首字符为!表示UTF时间

如果已经是UTC时间直接返回

修改并返回自�?
### timeOleObject.utc(true)

将本地时间转换为UTC时间

并创建一个新的时间对象返�?
如果已经是UTC时间直接复制并返�?
不修改自身并返回新对�?
### timeOleObject.year

�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/time/ole.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/time/ole.md')

