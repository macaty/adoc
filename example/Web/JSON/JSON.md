[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: web.json �?- JSON 解析

```aardio aardio
//web.json �?-  JSON 解析
//参�?『工�?�?编码 �?JSON / table 互转�?
import web.json;
import console;

//web.json 有很好的兼容性，写法非常自由�?var json = /*******
//这是注释

#这也是注�?
/*
如果根节点是一个对象，可以省略外层�?{}
*/
name = {
    a: 123,
    b: 456,
    c: [1,2,3]
}
tm: 2021-02-1T15:02:31+08:00 //可以使用ISO 8601格式表示日期时间
名字 = 值，可以使用等号分隔键�?名字2: 值，也可以用冒号分隔键�?名字3  值，甚至可以不使用分隔符，用空格分开就可�?
名字4
这样写也可以

名字5
这样写也没问�?
"名字6":"完全兼容传统的JSON语法",
名字7: 分隔符也可以使用分号;
名字8: 分隔符可以不写也没问�?名字9:  null //支持 null 值（虽然�?aardio �?null 等效于删除变�?�?*******/

//JSON 字串解码�?table 对象
var tabObject  = web.json.parse(json);
console.dumpJson( tabObject )
console.more(1);

// table 对象转换�?JSON 字符�?参数 @2 �?true 时格式化 JSON
var json = web.json.stringify(tabObject,true);
console.dump(json);

//再次使用 JSON 转换为对�?var jsonObject = web.json.parse(json);

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/JSON/JSON.md)

