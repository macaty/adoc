[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# string.chineseNumber 库模块帮助文�?
## string 成员列表

### string.chineseNumber()

[返回对象:stringChineseNumberObject](#stringChineseNumberObject)

### string.chineseNumber(中文数字,单位,万亿单位)

创建中文数值转换对�?所有参数可省略,

参数详细用法请参考库源码

## stringChineseNumberObject 成员列表

### stringChineseNumberObject.date(时间,格式化串,语言)

中文化日�?

兼容 time 对象构造函数全部参�?

所有参数可省略

### stringChineseNumberObject.datetime(时间,格式化串,语言)

中文化日期时�?

兼容 time 对象构造函数全部参�?

所有参数可省略

### stringChineseNumberObject.lang

格式化时间语言，默认自动选择 "chs" �?"cht"

### stringChineseNumberObject.minusChar

简体语言默认值为'�?，繁体语言默认值为'�?

### stringChineseNumberObject.money(数�?完整转换,简化十�?

数字转换为金�?

参数 @2 �?true 时允许返回零角零�?

参数 @3�?true 时简化一十为�?
### stringChineseNumberObject.moneyUnitChars

简体语言默认值为"元角�?，繁体语言默认值为"圓角�?

### stringChineseNumberObject.number(数�?简化十�?

数字转换为中�?包含单位,

参数 @1 也可以用文本指定 10 进制数值（支持大数,首字符为0时不清除�?

参数 @2 �?true 简化一十为十，参数 @1 首字符不�?0 时参�?@2 默认值为 true

### stringChineseNumberObject.numberChars

默认值为'零一二三四五六七八九'

### stringChineseNumberObject.onlyChar

默认值为"�?

### stringChineseNumberObject.pointChar

简体语言默认值为'�?，繁体语言默认值为'�?

### stringChineseNumberObject.replace(数�?

数字替换为中�?不包含单�?
### stringChineseNumberObject.time(时间,格式化串,语言)

中文化时�?

兼容 time 对象构造函数全部参�?

所有参数可省略

### stringChineseNumberObject.unitChars

默认值为'十百�?

### stringChineseNumberObject.wanUnitChars

简体语言默认值为'万亿'，繁体语言默认值为'萬億'

### stringChineseNumberObject.wanwan

大数单位万万�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/string/chineseNumber.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/string/chineseNumber.md')

