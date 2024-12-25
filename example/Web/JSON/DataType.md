[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: web.json �?- 特殊数据类型

```aardio aardio
//web.json �?-  特殊数据类型
import console;
import web.json;

/*
�?aardio 中对象与数组的数据类型都�?"table"�?所以在 aardio 中空对象与空数组都是 {} �?
使用 table.array() 则可以创�?JSON 兼容的空数组�?web.json 也会�?JSON 中的 "[]" 解析�?table.array() 创建的空数组�?*/

//定义 JSON
var json = "{ items = [] }";

//转换为对象，items 解析�?table.array() 创建的空数组�?var object = web.json.parse(json);

//添加数组字段
object.items2 = table.array(); //空数�?object.items3 = {1,2,3}; //非空数组直接兼容

//转换为数�?var json = web.json.stringify(object);
console.log(json)

//web.json.stringifyArray 总是将参数视为数组处理�?var json = web.json.stringifyArray({});
console.log(json)

/*
�?aardio �?null 是一个不存在的值�?例如 { name = null } 等价于空�?{} �?
而在 JSON 中我们有时候需要保�?null 值�?aardio 通过在元表的 _defined 字段中指定必须保�?null 值的字段名�?可以调用 table.define() 定义需要保�?null 值的键名（可以重复调用以添加键名）�?web.json �?table.eachName 支持 _defined 元属性�?*/

//定义 JSON
var json = "{name:null,age:22}";

//解析为对�?var object = web.json.parse(json);

//生成 JSON
var json = web.json.stringify(object);

console.log(json);

/*
时间对象�?JS 语言相同转换�?ISO8601 格式字符串�?time 对象�?JS 一样只负责字符串化,不负责在解析 JSON 时自动还原�?应使�?time.iso8601 函数解析 iso8601 格式的时间�?*/

//定义对象
var object = { time = time() };

//生成 JSON
var json = web.json.stringify(object);

//解析为对�?var object = web.json.parse(json);

var tm = time.iso8601(object.time);
console.log( tostring(tm,"%c")  )

/*
buffer 类与 node.js 中的 Buffer 类转换结果类似�?{"data":[230,181,139],"type":"Buffer"}
其中 type 指明类型,data �?buffer 字节数组的值�?
buffer,

�?raw.buffer 的参数中使用结构体还原字节数组�?*/

//定义 buffer
var buffer = raw.buffer("abc");

//生成 JSON
var json = web.json.stringify(buffer);

//解析为对�?var bufferObject = web.json.parse(json);

//可以作为参数快速还原为 buffer
var buffer = raw.buffer(bufferObject)

console.log(buffer);
console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/JSON/DataType.md)

