[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.sciter.valueObject 库模块帮助文�?
## web.sciter 成员列表

### web.sciter.isValueObject()

检测一个值是否web.sciter.valueObject对象

### web.sciter.makeError()

此函数返回错误值对象（ web.sciter.valueObject 对象 �?
参数指定要设置的错误信息

[返回对象:webSciterValueObject](#webSciterValueObject)

### web.sciter.valueObject()

[返回对象:webSciterValueObject](#webSciterValueObject)

### web.sciter.valueObject(初始�?单位,类型)

创建并返回动态值类�?

所有参数可�?
### web.sciter.valueObjectLite()

无GC值对�?避免自动释放,

[返回对象:webSciterValueObject](#webSciterValueObject)

## webSciterValueObject 成员列表

### webSciterValueObject.addRef()

添加引用计数

### webSciterValueObject.clear()

清空�?
### webSciterValueObject.clone()

复制�?
[返回对象:webSciterValueObject](#webSciterValueObject)

### webSciterValueObject.enum(枚举函数)

```aardio aardio
webSciterValueObject.enum(
    function(k,v ){
        io.print( k,v )
    }
)

```

### webSciterValueObject.getBinary()

返回 buffer 类型字节数组

零长度数组返�?null

### webSciterValueObject.getEle()

返回节点对象,

注意:节点类型只能读取不能写入

### webSciterValueObject.getInt32()

返回整型数�?
如果值类型不是整型�?取值返回空

### webSciterValueObject.getItem()

[返回对象:webSciterValueObject](#webSciterValueObject)

### webSciterValueObject.getItem(索引)

获取成员

### webSciterValueObject.getLong64()

返回长整型数�?
如果值类型不是长整型数�?取值返回空

### webSciterValueObject.getNumber()

返回浮点数�?
如果值类型不是浮点数,取值返回空

使用 tonumber() 函数可强制返回数�?
### webSciterValueObject.getString()

返回字符串�?
如果值类型字符串�?取值返回空

使用 tostring() 函数可强制返回数�?
### webSciterValueObject.getTime()

返回时间�?
如果值类型不是时间�?取值返回空

### webSciterValueObject.getType()

返回值类�?_HL\_T_ 前缀常量表示

### webSciterValueObject.getValue()

返回字符串值、数值、时间�?
### webSciterValueObject.isArray()

是否数组对象

### webSciterValueObject.isDomObject()

是否节点对象,

使用 getEle()函数转换为节点对�?
### webSciterValueObject.isErrorString()

值是错误信息

### webSciterValueObject.isMap()

是否键值表对象

### webSciterValueObject.isScriptArray()

值是脚本返回的数组对�?
### webSciterValueObject.isScriptClass()

值是脚本返回的类对象

### webSciterValueObject.isScriptError()

脚本类型错误

### webSciterValueObject.isScriptFunction()

值是脚本返回的函数对�?
### webSciterValueObject.isScriptNative()

值是脚本返回的本地函数对�?
### webSciterValueObject.isScriptObject()

值是脚本返回的对�?
### webSciterValueObject.isScriptValue()

值是脚本返回的对�?
所有脚本类型都返回 true

### webSciterValueObject.isSymbolString()

值是符号

### webSciterValueObject.jsonParse('{ k:"v" }')

解析JSON字符�?
### webSciterValueObject.jsonStringify()

转换并返回JSON字符�?
### webSciterValueObject.length

数组长度

### webSciterValueObject.makeError()

返回 JavaScript 错误对象,参数指定要设置的错误信息,

此函数返回自�?
[返回对象:webSciterValueObject](#webSciterValueObject)

### webSciterValueObject.parse("10pt")

解析字符�?
### webSciterValueObject.scriptIsolate()

脚本对象转换为MAP,或ARRAY类型

### webSciterValueObject.setBinary(buffer,len)

设置二进制字节数�?

如果参数@1是buffer、字符串,可选用参数@2指定长度,

如果参数@1是指�?则必须指定长�?
### webSciterValueObject.setInt32(数�?

写入整型数�?
### webSciterValueObject.setItem(索引,�?

设置成员�?
### webSciterValueObject.setLong64(数�?

写入长整型数�?
### webSciterValueObject.setNumber(数�?

写入浮点数�?
### webSciterValueObject.setString(字符串�?

写入字符串�?
### webSciterValueObject.setTime(时间�?

写入时间�?
### webSciterValueObject.setValue(�?单位,类型)

写入字符串值、数值、时间�?
参数2,参数3为可选参�?
### webSciterValueObject.stringify()

转换并返回字符串

### webSciterValueObject.value

读取或写入字符串值、数值、时间�?
### webSciterValueObject.xcall

调用 Javascript 函数

### webSciterValueObject.xcall(urlOrScriptName,thisObject,...)

调用 Javascript 函数,

urlOrScriptName,thisObject 可省�?

thisObject 可选用于指�?JS 函数�?this 对象,

可添加任意个调用参数

可以省略 xcall 函数名，直接将对象作为函数调�?

省略 xcall 函数名时不需要指�?urlOrScriptName,thisObject 参数

### 自动完成常量

\_HL\_CVT\_JSON\_LITERAL=1

\_HL\_CVT\_JSON\_MAP=2

\_HL\_CVT\_SIMPLE=0

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/sciter/valueObject.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/sciter/valueObject.md')

