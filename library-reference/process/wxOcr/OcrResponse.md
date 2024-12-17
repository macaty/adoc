[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# process.wxOcr.OcrResponse 库模块帮助文�?
## process.wxOcr.OcrResponse 成员列表

Protobuf 消息对象

### process.wxOcr.OcrResponse.OcrResult()

创建 Protobuf 消息对象�?
[返回对象:bfc37b1asponseOcrResultObject](#bfc37b1asponseOcrResultObject)

## 58d30c14ResultPosPosXYObject 成员列表

### 58d30c14ResultPosPosXYObject.eachName()

```aardio aardio
for k,v in 58d30c14ResultPosPosXYObject.eachName(){
                /*遍历此消息对象的所有字段，
            k 为字段名,v 为字段值�?/
            }

```

### 58d30c14ResultPosPosXYObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### 58d30c14ResultPosPosXYObject.serializeToString()

序列化消息对�?返回二进制字符串

### 58d30c14ResultPosPosXYObject.x

```aardio aardio
protobuf.type.float

```

### 58d30c14ResultPosPosXYObject.y

```aardio aardio
protobuf.type.float

```

## 7671c335ResultResultPosObject 成员列表

### 7671c335ResultResultPosObject.eachName()

```aardio aardio
for k,v in 7671c335ResultResultPosObject.eachName(){
        /*遍历此消息对象的所有字段，
    k 为字段名,v 为字段值�?/
    }

```

### 7671c335ResultResultPosObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### 7671c335ResultResultPosObject.pos

不作为函数调用时，用于返回或设置数组�?
### 7671c335ResultResultPosObject.pos()

[返回对象:58d30c14ResultPosPosXYObject](#58d30c14ResultPosPosXYObject)

### 7671c335ResultResultPosObject.pos(index,value)

如果作为函数调用�?
修改值时参数 @index 指定元素索引，参�?@value 指定元素值�?
获取值时用参�?@index 指定数组索引即可

### 7671c335ResultResultPosObject.serializeToString()

序列化消息对�?返回二进制字符串

## a35ef3b6ResultOneResultObject 成员列表

### a35ef3b6ResultOneResultObject.eachName()

```aardio aardio
for k,v in a35ef3b6ResultOneResultObject.eachName(){
                /*遍历此消息对象的所有字段，
            k 为字段名,v 为字段值�?/
            }

```

### a35ef3b6ResultOneResultObject.onePos

[返回对象:7671c335ResultResultPosObject](#7671c335ResultResultPosObject)

### a35ef3b6ResultOneResultObject.oneStrUtf8

```aardio aardio
protobuf.type.bytes

```

### a35ef3b6ResultOneResultObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### a35ef3b6ResultOneResultObject.serializeToString()

序列化消息对�?返回二进制字符串

## bfc37b1asponseOcrResultObject 成员列表

### bfc37b1asponseOcrResultObject.eachName()

```aardio aardio
for k,v in bfc37b1asponseOcrResultObject.eachName(){
    /*遍历此消息对象的所有字段，
k 为字段名,v 为字段值�?/
}

```

### bfc37b1asponseOcrResultObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### bfc37b1asponseOcrResultObject.serializeToString()

序列化消息对�?返回二进制字符串

### bfc37b1asponseOcrResultObject.singleResult

不作为函数调用时，用于返回或设置数组�?
### bfc37b1asponseOcrResultObject.singleResult()

[返回对象:d12690daultSingleResultObject](#d12690daultSingleResultObject)

### bfc37b1asponseOcrResultObject.singleResult(index,value)

如果作为函数调用�?
修改值时参数 @index 指定元素索引，参�?@value 指定元素值�?
获取值时用参�?@index 指定数组索引即可

### bfc37b1asponseOcrResultObject.unknown\_1

repeated 每行的结�?
protobuf.type.int32

### bfc37b1asponseOcrResultObject.unknown\_2

```aardio aardio
protobuf.type.int32

```

## d12690daultSingleResultObject 成员列表

### d12690daultSingleResultObject.eachName()

```aardio aardio
for k,v in d12690daultSingleResultObject.eachName(){
        /*遍历此消息对象的所有字段，
    k 为字段名,v 为字段值�?/
    }

```

### d12690daultSingleResultObject.lx

```aardio aardio
protobuf.type.float

```

### d12690daultSingleResultObject.ly

识别矩形的左上和右下的坐�? 可能�?
protobuf.type.float

### d12690daultSingleResultObject.oneResult

不作为函数调用时，用于返回或设置数组�?
### d12690daultSingleResultObject.oneResult()

[返回对象:a35ef3b6ResultOneResultObject](#a35ef3b6ResultOneResultObject)

### d12690daultSingleResultObject.oneResult(index,value)

如果作为函数调用�?
修改值时参数 @index 指定元素索引，参�?@value 指定元素值�?
获取值时用参�?@index 指定数组索引即可

### d12690daultSingleResultObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### d12690daultSingleResultObject.rx

```aardio aardio
protobuf.type.float

```

### d12690daultSingleResultObject.ry

```aardio aardio
protobuf.type.float

```

### d12690daultSingleResultObject.serializeToString()

序列化消息对�?返回二进制字符串

### d12690daultSingleResultObject.singlePos

SingleResult是一行结�?OneResult是单字的

[返回对象:7671c335ResultResultPosObject](#7671c335ResultResultPosObject)

### d12690daultSingleResultObject.singleRate

UTF8格式的字符串

protobuf.type.float

### d12690daultSingleResultObject.singleStrUtf8

```aardio aardio
protobuf.type.bytes

```

### d12690daultSingleResultObject.unknownPos

未知

[返回对象:7671c335ResultResultPosObject](#7671c335ResultResultPosObject)

### d12690daultSingleResultObject.unknown\_0

```aardio aardio
protobuf.type.int32

```

## process.wxOcr 成员列表

### process.wxOcr.OcrResponse()

创建 Protobuf 消息对象�?
[返回对象:processWxOcrOcrResponseObject](#processWxOcrOcrResponseObject)

## process.wxOcr.OcrResponse.OcrResult 成员列表

Protobuf 消息对象

### process.wxOcr.OcrResponse.OcrResult.ResultPos()

创建 Protobuf 消息对象�?
[返回对象:7671c335ResultResultPosObject](#7671c335ResultResultPosObject)

### process.wxOcr.OcrResponse.OcrResult.SingleResult()

创建 Protobuf 消息对象�?
[返回对象:d12690daultSingleResultObject](#d12690daultSingleResultObject)

## process.wxOcr.OcrResponse.OcrResult.ResultPos 成员列表

Protobuf 消息对象

### process.wxOcr.OcrResponse.OcrResult.ResultPos.PosXY

Protobuf 消息对象

### process.wxOcr.OcrResponse.OcrResult.ResultPos.PosXY()

创建 Protobuf 消息对象�?
[返回对象:58d30c14ResultPosPosXYObject](#58d30c14ResultPosPosXYObject)

## process.wxOcr.OcrResponse.OcrResult.SingleResult 成员列表

Protobuf 消息对象

### process.wxOcr.OcrResponse.OcrResult.SingleResult.OneResult

Protobuf 消息对象

### process.wxOcr.OcrResponse.OcrResult.SingleResult.OneResult()

创建 Protobuf 消息对象�?
[返回对象:a35ef3b6ResultOneResultObject](#a35ef3b6ResultOneResultObject)

## processWxOcrOcrResponseObject 成员列表

### processWxOcrOcrResponseObject.eachName()

```aardio aardio
for k,v in processWxOcrOcrResponseObject.eachName(){
    /*遍历此消息对象的所有字段，
k 为字段名,v 为字段值�?/
}

```

### processWxOcrOcrResponseObject.errCode

```aardio aardio
protobuf.type.int32

```

### processWxOcrOcrResponseObject.ocrResult

[返回对象:bfc37b1asponseOcrResultObject](#bfc37b1asponseOcrResultObject)

### processWxOcrOcrResponseObject.parseFromString(字符�?

二进制数据反序列化到消息对象

此函数自动清空所有数组�?但不会重置其他非数组字段�?

因此应对新创建的对象调用此函�?

### processWxOcrOcrResponseObject.serializeToString()

序列化消息对�?返回二进制字符串

### processWxOcrOcrResponseObject.taskId

第一次运行OCR会有push一次type1, 正常OCR结束type0

protobuf.type.int32

### processWxOcrOcrResponseObject.type

```aardio aardio
protobuf.type.int32

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/process/wxOcr/OcrResponse.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/process/wxOcr/OcrResponse.md')

