[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.layout.valueObject 库模块帮助文�?
## web.layout 成员列表

### web.layout.valueObject()

[返回对象:webLayoutValueObject](#webLayoutValueObject)

### web.layout.valueObject(初始�?单位,类型)

创建并返回动态值类�?

所有参数可�?
### web.layout.valueObjectLite()

无GC值对�?避免自动释放,

[返回对象:webLayoutValueObject](#webLayoutValueObject)

## webLayoutValueObject 成员列表

### webLayoutValueObject.addRef()

添加引用计数

### webLayoutValueObject.clear()

清空�?
### webLayoutValueObject.clone()

复制�?
[返回对象:webLayoutValueObject](#webLayoutValueObject)

### webLayoutValueObject.enum(枚举函数)

```aardio aardio
webLayoutValueObject.enum(
    function(k,v ){
        io.print( k,v )
    }
)

```

### webLayoutValueObject.getBinary()

返回 buffer 类型字节数组

零长度数组返�?null

### webLayoutValueObject.getEle()

返回节点对象,

注意:节点类型只能读取不能写入

### webLayoutValueObject.getInt32()

返回整型数�?
如果值类型不是整型�?取值返回空

### webLayoutValueObject.getItem()

[返回对象:webLayoutValueObject](#webLayoutValueObject)

### webLayoutValueObject.getItem(索引)

获取成员

### webLayoutValueObject.getLong64()

返回长整型数�?
如果值类型不是长整型数�?取值返回空

### webLayoutValueObject.getNumber()

返回浮点数�?
如果值类型不是浮点数,取值返回空

使用 tonumber() 函数可强制返回数�?
### webLayoutValueObject.getString()

返回字符串�?
如果值类型字符串�?取值返回空

使用 tostring() 函数可强制返回数�?
### webLayoutValueObject.getTime()

返回时间�?
如果值类型不是时间�?取值返回空

### webLayoutValueObject.getType()

返回值类�?_HL\_T_ 前缀常量表示

### webLayoutValueObject.getValue()

返回字符串值、数值、时间�?
### webLayoutValueObject.isArray()

是否数组对象

### webLayoutValueObject.isDomObject()

是否节点对象,

使用 getEle()函数转换为节点对�?
### webLayoutValueObject.isMap()

是否键值表对象

### webLayoutValueObject.jsonParse('{ k:"v" }')

解析JSON字符�?
### webLayoutValueObject.jsonStringify()

转换并返回JSON字符�?
### webLayoutValueObject.length

数组长度

### webLayoutValueObject.parse("10pt")

解析字符�?
### webLayoutValueObject.setBinary(buffer,len)

设置二进制字节数�?

如果参数@1是buffer、字符串,可选用参数@2指定长度,

如果参数@1是指�?则必须指定长�?
### webLayoutValueObject.setInt32(数�?

写入整型数�?
### webLayoutValueObject.setItem(索引,�?

设置成员�?
### webLayoutValueObject.setLong64(数�?

写入长整型数�?
### webLayoutValueObject.setNumber(数�?

写入浮点数�?
### webLayoutValueObject.setString(字符串�?

写入字符串�?
### webLayoutValueObject.setTime(时间�?

写入时间�?
### webLayoutValueObject.setValue(�?单位,类型)

写入字符串值、数值、时间�?
参数2,参数3为可选参�?
### webLayoutValueObject.stringify()

转换并返回字符串

### webLayoutValueObject.value

读取或写入字符串值、数值、时间�?
### 自动完成常量

\_HL\_CVT\_JSON\_LITERAL=1

\_HL\_CVT\_JSON\_MAP=2

\_HL\_CVT\_SIMPLE=0

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/layout/valueObject.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/layout/valueObject.md')

