[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: main

```aardio aardio
import console;

//编译 proto文件,生成类库
import protobuf.parser;
if(!protobuf.parser)
    return;

var p = protobuf.parser();
p.parseFile("\res\test.proto",,false)

//导入生成的类�?import AddressBook
import Person

//读取数据文件
book = AddressBook();
var str = string.load("\res\test.pb" );
book.parseFromString(str);

//遍历所有字�?for k,v in book.eachName(){
    console.log(k,v)
}

//支持转换�?JSON
console.dumpJson(book)

//访问数组元素
person = book.person[1]
console.log("用户�?,person.name );
console.log(person.id );
console.log(person.email );
console.log("电话号码数目",#person.phone );
console.log("-------------------")

person = book.person[2]
console.log("用户�?,person.name );
console.log(person.id );
console.log(person.email );
console.log("电话号码数目",#person.phone );

//遍历数组，用 # 操作符取数组长度
for( i=1;#person.phone ){
    console.log(i,person.phone[i].number )
}
console.log("-------------------")

console.log("请右键点�?工程->用户�?,在弹出菜单中点击'刷新目录' ")
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/protobuf/SampleProjects/main.md)

