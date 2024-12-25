[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.guid 库模块帮助文�?
## win 成员列表

### win.guid("GUID、CLSID、ProgID�?)

字符串转换为 GUID,

参数支持ProgID,CLSID,GUID,

失败返回null空�?
### win.guid()

创建 GUID 结构�?初始化为空�?

此对象可以使�?tostring 函数转换为大写字符串,

tostring 参数@2指定是否小写,参数@3指定是否添加大括�?

tostring 参数@2 也可用字符串指定11个数值参数的格式化串,

[返回对象:winGuidObject](#winGuidObject)

### win.guid(数�?数�?数�?'\\x00\\x00\\x00\\x00\\x00\\x00\\x00\\x00')

创建GUID结构�?
参数@4也可以改为包�?个字节数值的数组或者展开�?个数值参�?
## win.guid 成员列表

### win.guid.create()

创建 GUID 结构体并初始化为唯一�?
[返回对象:winGuidObject](#winGuidObject)

### win.guid.fromString("字符串参�?)

字符串转换为 GUID

参数支持ProgID,CLSID,GUID,

失败返回null空�?
注意 win.guid 对象可以使用 tostring 函数转换为字符串,

tostring 参数@1指定是否小写,参数@2指定是否添加大括�?

[返回对象:winGuidObject](#winGuidObject)

### win.guid.fromString()

[返回对象:winGuidObject](#winGuidObject)

### win.guid.toProgId("字符串参�?)

GUID转换为字符串格式�?ProgId

失败返回null空�?
### win.guid.valid()

[返回对象:winGuidObject](#winGuidObject)

### win.guid.valid(GUID对象)

判断是否有效GUID对象,

如果参数是ProgID,CLSID,GUID,则尝试转�?

转换成功则返回GUID对象,否则返回�?
## winGuidObject 成员列表

### winGuidObject.Data1

INT类型

### winGuidObject.Data2

WORD类型

### winGuidObject.Data3

WORD类型

### winGuidObject.Data4

字符串�?也可以指定包含多个字节值的数组

### winGuidObject.create()

初始化为唯一值，返回自身

[返回对象:winGuidObject](#winGuidObject)

### winGuidObject.fromString("字符串参�?)

字符串转换为 GUID 结构�?返回自身,

也可以直接写�?win.guid 参数�?

可使�?tostring 函数�?GUID 结构体重新转换为字符�?
tostring 参数@2指定是否小写,参数@3指定是否添加大括�?

tostring 参数@2 也可用字符串指定11个数值参数的格式化串

[返回对象:winGuidObject](#winGuidObject)

### winGuidObject.hex()

转换�?6进制格式

返回值可以置入单引号转义字符串内使用

### winGuidObject.isNull()

是否等于GUID\_NULL，也就是结构体内存的所有字节值为0

### winGuidObject.toProgId()

CLSID转换为ProgId,返回字符�?
### winGuidObject.toString

转换为字符串,也支持通过 tostring 自动调用此函�?
### winGuidObject.toString("%08X%04X%04X%02X%02X%02X%02X%02X%02X%02X%02X")

转换为字符串,自定�?11 个数值参数的格式化串

### winGuidObject.toString(是否小写,是否添加大括�?

转换为字符串,生成格式:

00000000-0000-0000-0000-000000000000

### winGuidObject.unpack()

转换并返�?11 个数�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/guid.md)

