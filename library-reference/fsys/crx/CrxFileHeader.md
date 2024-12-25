[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.crx.CrxFileHeader 库模块帮助文�?
## fsys.crx 成员列表

### fsys.crx.CrxFileHeader

Protobuf 消息对象

### fsys.crx.CrxFileHeader()

创建 Protobuf 消息对象�?
[返回对象:fsysCrxCrxFileHeaderObject](#fsysCrxCrxFileHeaderObject)

## fsysCrxCrxFileHeaderObject 成员列表

### fsysCrxCrxFileHeaderObject.crxId

扩展 ID，仅解包 crx 后可用�?
### fsysCrxCrxFileHeaderObject.eachName()

```aardio aardio
for k,v in fsysCrxCrxFileHeaderObject.eachName(){
    /*遍历此消息对象的所有字段，
k 为字段名,v 为字段值�?/
}

```

### fsysCrxCrxFileHeaderObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### fsysCrxCrxFileHeaderObject.parseValue()

调用 table.parseValue 获取纯值表�?
纯值表只包含纯值类型数据，

纯值类型指的是：字符串、数值、布尔值、buffer、指针、纯值表�?
纯值表要么是数组，要么是包含名值对的表�?
纯值表是可保持原值序列化的表，并且兼�?JSON

### fsysCrxCrxFileHeaderObject.serializeToString()

序列化消息对�?返回二进制字符串

### fsysCrxCrxFileHeaderObject.sha256WithEcdsa

ECDSA 公钥与签名�?
不作为函数调用时，用于返回或设置数组�?
### fsysCrxCrxFileHeaderObject.sha256WithEcdsa()

[返回对象:fsysCrxAsymmetricKeyProofObject](#fsysCrxAsymmetricKeyProofObject)

### fsysCrxCrxFileHeaderObject.sha256WithEcdsa(index,value)

ECDSA 公钥与签名。n如果作为函数调用�?
修改值时参数 @index 指定元素索引，参�?@value 指定元素值�?
获取值时用参�?@index 指定数组索引即可

### fsysCrxCrxFileHeaderObject.sha256WithRsa

公钥�?sha256 签名。不作为函数调用时，用于返回或设置数组�?
### fsysCrxCrxFileHeaderObject.sha256WithRsa()

[返回对象:fsysCrxAsymmetricKeyProofObject](#fsysCrxAsymmetricKeyProofObject)

### fsysCrxCrxFileHeaderObject.sha256WithRsa(index,value)

公钥�?sha256 签名�?
如果作为函数调用�?
修改值时参数 @index 指定元素索引，参�?@value 指定元素值�?
获取值时用参�?@index 指定数组索引即可

### fsysCrxCrxFileHeaderObject.signedHeaderData

签名数据.

protobuf.type.bytes

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/crx/CrxFileHeader.md)

