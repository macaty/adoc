[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# web.json 库模块帮助文�?
用前必读，点这里展开

# 相关工具与范�?
『工�?�?编码 �?JSON / table 互转�?『范�?�?Web 应用 �?JSON �?『范�?�?Web 应用 �?REST �?jsonClient�?
# aardio / JSON 类型转换要点

#### 一、区分空对象与空数组

�?aardio 中对象与数组的数据类型都�?"table"�?所以在 aardio 中空对象与空数组都是 {} �?
对于 web.json，{} 总是被处理为空对象�?使用 table.array() 则可以创�?JSON 兼容的空数组�?web.json 也会�?JSON 中的 "\[\]" 解析�?table.array() 创建的空数组�?
aardio 通常会在表的 \_type 元属性中指定一个表是否数组�?�?table.array() 创建的空数组是这�?{ @{\_type="array"}}�?或者长度非 0 的数组也会被视为数组，例�?{ 1,2,3 } �?
但还有很多其他来源的数组（例�?COM 数组，封装外部对象的数组）并不一定符合上面的规则�?web.json 使用 table.type() 函数来检测一个表是否应当被处理为数组�?详细规则请查�?table.type() 函数的说明�?
也可以使�?web.json.stringifyArray("{}") 得到 "\[\]"�?web.json.stringifyArray 总是将参数视为数组处理�?
#### 二、保存对象的 null 值�?
�?aardio �?null 是一个不存在的值�?例如 { name = null } 等价于空�?{} �?
而在 JSON 中我们有时候需要保�?null 值�?这在 aardio 中很困难，但我们可以解决这个问题�?
例如以下 aardio 代码�?
```
//定义 JSON
var json = "{name:null,age:22}";

//解析为对�?var object = web.json.parse(json);

//生成 JSON
var json = web.json.stringify(object);

```

可以正确的保�?name �?null 值�?
aardio 通过在元表的 \_defined 字段中指定必须保�?null 值的字段名�?可以调用 table.define() 定义需要保�?null 值的键名（可以重复调用以添加键名）�?web.json �?table.eachName 支持 \_defined 元属性�?
#### 三、时�?�?buffer 对象

buffer,time 对象�?JS 一样只负责字符串化，不负责在解�?JSON 时自动还原�?
时间对象�?JS 语言相同转换�?ISO8601 格式字符串，
可使�?time.iso8601 函数解析并还�?iso8601 格式的时间对象�?
buffer 类与 node.js 中的 Buffer 类相�?转换结果示例�?{"data":\[230,181,139\],"type":"Buffer"}
其中 type 指明类型,data �?buffer 字节数组的值�?这种表可以作�?raw.buffer 的唯一参数快速还原为 buffer 类型�?
# aardio-json 扩展标准

发布日期�?020-12-27

JSON 字符串化时完全符�?JSON 官方标准( [https://json.org/json-zh.html](javascript:if(confirm('https://json.org/json-zh.html  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ����һ������·���ⲿ������Ϊ������ʼ��ַ�ĵ�ַ��  \n\n�����ڷ������ϴ�����?'))window.location='https://json.org/json-zh.html') )�?JSON 解析时完全支�?JSON，JSONP，并使用宽松的原则兼容JSON5，兼容部分类 YAML 语法�?
aardio-json 以“宽进严出、简洁高效”为基本原则�?解析时规则尽可能宽松容错，生�?JSON 字符串则严格遵守标准JSON规则�?为了让解析器尽可能做到简洁高效，所�?aardio-json 不支持变量，
真正简洁高效的配置文件不应当出现重复的内容，JSON 的目标也不是成为编程语言�?
一、可省略和替换的格式标记
1、允许省略根节点对象外部�?{}
2、允许使用分号、空格、换行替代元素分隔符","
3、允许使用等号、空格、换行替代对象键值分隔符":"
4、允许省略字符串外部的引号�?
二：根节�?1、JSON根节点可以是任意数据类型，单个字符串、数值都可以解析并返回值�?2、根节点是对象时，可以省略外层的花括号�?3、根节点是字符串时不可省略引号�?4、根节点解析成功�?JSON 后面如果还有多余的文本时忽略�?5、根节点兼容 JSONP 格式

三、字符串
字符串置于双引号中时支持JSON转义符�?字符串置于单引号中时不支持JSON转义符，单引号中可使�?个单引号表示原始单引号�?字符串可以在引号内部时可以换行�?
要特别注意原生的 aardio 字符串解析语法正好跟上面相反�?单引号中是转义字符串，而双引号内是非转义字符串�?
JSON 字符串可省略首尾引号，此时不支持JSON转义符，遇到回车或换行、逗号、中括号、大括号时字符串结束解析�?字符串作为对象键名如果省略引号时不能包含空白字符、换行或键值分隔符�?
四、注�?1、支�?`//` �?`#` 引导的单行注�?2、支持包含于 `/*......*/` 内的块注释（注意这里按js规则不匹配首尾星号数目）�?
五、数�?数值支�?6进制

六、null�?可以使用null,undefined,~ 表示null值�?
七、日期时�?
可使�?ISO 8601 格式表示日期时间，合法的格式如下�?2021-01-1
2021-02-1T15:02:31+08:00
2021-02-1T15:02:31+08:00Z

数字前可不用�?，但日期分隔符必须使用短横线，时间分隔符必须使用冒号�?尾部时区不可以包含空白字符，但可以包�?+-: 等字符以及数字、字母�?
## web.json 成员列表

JSON 解析�?

字符串化时完全符�?JSON 官方标准�?
解析使用 aardio-json 扩展语法，兼容JSON，JSONP，JSON5，部分类YAML语法,

存取大容量数据请改用数据库组�?
### web.json.ndParse

解析 ndjson，也就是每行一�?JSON �?
兼容 JSON 行分隔符�?`'\r'`�?\\r

'�?

'�?`'\x1E'` �?
此函数忽略错误行，错误行不会抛出异常�?
但会通过 io.stderr.write 函数输出错误信息与出�?JSON

### web.json.ndParse(输入文本,是否解析转义�?

解析 ndjson�?
只能输入 UTF-8 文本，字符串不能�?BOM 编码头（一般也不可能有�?
### web.json.parse

使用宽松�?JSON 语法解析并返回表对象,

支持自动检测输入字符串�?Unicode BOM,

除完全支�?JSON 标准之外，并可兼�?jsonp，json5，支�?aardio-json 扩展标准�?
### web.json.parse(输入文本,是否解析转义�?输入代码�?

参数@2默认�?true,

代码页默认为 65001 �?UTF-8 编码,

输入文本如使用了 UTF-16 LE/BE 编码则转换为 UTF-8,

返回对象的元�?\_defined 字段记录了所有已定义的键,

参数传入空值或空字符串返回空�?
解析误到错误�?JSON 语法时会抛出异常

### web.json.stringify

转换为参�?@1 �?JSON 文本

表对象可在元�?\_defined 字段中预定义可能�?null 值的�?

也可以在 \_json 元方法中返回一个自定义的对象用于转换为 JSON�?
注意 {} 为空对象，table.array 创建 JSON 空数组，详见 table.type 函数说明�?
关于时间对象�?buffer 对象的转换规则请查看 web.json 文档�?
以及：范�?/ web 应用 / JSON / 特殊数据类型

### web.json.stringify(对象,是否格式�?是否使用UNICODE编码)

参数@2,@3可�?默认不格式化,启用UNICODE编码

如果指定格式�?参数@3则默认为false

注意即使选择了不启用UNICODE编码，单引号�?
以及一些可能无法直接显示的Unicode字符仍然会进行转�?

表对象中值不是表对象的成员先列出

### web.json.stringifyArray(�?是否格式�?是否使用UNICODE编码,是否清除null�?

如果参数@1未声明数组类型，则添加类型声�?

空数组会返回\[\]而不是{},其他参数与web.json.stringify相同

### web.json.strip()

将一个对象转换为 JSON ,再转换为 aardio 纯值类型对象�?
纯值类型指的是字符串、数值、布尔值、buffer、指针、纯值表�?
关于纯值与纯值表可参�?table.parseValue 函数的说明�?
纯值支持原值序列化，并�?JSON 兼容�?
web.json.strip 兼容 Python 对象�?
如果提前导入 dotNet.json �?
则可以用此函数将 .NET 对象转为 aardio 纯值对�?
### web.json.tryParse(输入文本,是否解析转义�?输入代码�?

解析 JSON 并返�?aardio 对象

作用与参数用法与parse函数一�?

请参考该函数说明

唯一的区别是�?
parse函数遇到JSON语法错误时抛出异�?
而tryParse遇到错误时返�?null,错误信息

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/json.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/json.md')

