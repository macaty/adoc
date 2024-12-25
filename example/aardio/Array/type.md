[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 声明数组类型

```aardio aardio
//声明数组类型
import console.int;

/*
aardio 中表和数组是同一数据类型�?而类�?JSON 需要区分空表（ object ）与空数组（ array ）�?
�?aardio 中可以使�?table.array() 创建 JSON 兼容的空数组�?table.array() 返回的空数组对象会加上元属�?@{_type="array"}用于声明数组类型�?*/

var array = table.array();

//下面会显�?[] 而不�?{}
console.dumpJson(array);

/*
table.isArray() 的检测规则为�?如果参数不是 table 类型返回 false �?参数�?_type 元属性为 "object" 返回 false �?参数�?_type 元属性为 "array" 返回 true �?参数指定�?length 元属性或 length 属性返�?true �?参数对象包含数组成员返回 true �?其他情况返回 false �?*/
if(table.isArray(array)){
    console.log("array 是一个数�?)
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Array/type.md)

