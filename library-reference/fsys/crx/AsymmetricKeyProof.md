[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# fsys.crx.AsymmetricKeyProof 库模块帮助文�?
## fsys.crx 成员列表

### fsys.crx.AsymmetricKeyProof

Protobuf 消息对象

### fsys.crx.AsymmetricKeyProof()

创建 Protobuf 消息对象�?
[返回对象:fsysCrxAsymmetricKeyProofObject](#fsysCrxAsymmetricKeyProofObject)

## fsysCrxAsymmetricKeyProofObject 成员列表

### fsysCrxAsymmetricKeyProofObject.eachName()

```aardio aardio
for k,v in fsysCrxAsymmetricKeyProofObject.eachName(){
    /*遍历此消息对象的所有字段，
k 为字段名,v 为字段值�?/
}

```

### fsysCrxAsymmetricKeyProofObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### fsysCrxAsymmetricKeyProofObject.parseValue()

调用 table.parseValue 获取纯值表�?
纯值表只包含纯值类型数据，

纯值类型指的是：字符串、数值、布尔值、buffer、指针、纯值表�?
纯值表要么是数组，要么是包含名值对的表�?
纯值表是可保持原值序列化的表，并且兼�?JSON

### fsysCrxAsymmetricKeyProofObject.publicKey

```aardio aardio
protobuf.type.bytes

```

### fsysCrxAsymmetricKeyProofObject.serializeToString()

序列化消息对�?返回二进制字符串

### fsysCrxAsymmetricKeyProofObject.signature

```aardio aardio
protobuf.type.bytes

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/fsys/crx/AsymmetricKeyProof.md)

