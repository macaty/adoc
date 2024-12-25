[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: string.database �?- 读写 CSV 文件

```aardio aardio
//string.database �?- 读写 CSV 文件
import console;
import string.database;

//创建 CSV 数据库对�?var csv = string.database(",");

//CSV 格式测试数据
var txt = /*
Name,Starred,Contact_Id
"孟轲","0",0
*/

//解析数据
var csvTable = csv.parse(txt);
console.dump( csvTable ); //这里�?csvTable �?csv.dataTable 是同一个对�?
//添加多行数据�?csv.dataTable （也就是上面�?csvTable �?csv.push(
    {"张九�?,"1",1 },
    {"张九�?","2",2 }
);

//也可以添加一行的多个�?csv.push("张九�?","3",3);

//保存�?UTF-8 编码 CSV 文件
csv.save("/utf8.csv");

//参数 @3 �?true 则向文件追加数据
csv.save("/utf8.csv",{{ "孟轲2","2",2} },true);

//保存�?ANSI 编码 CSV 文件
csv.saveA("/ansi.csv");

//转换为文�?var str = csv.stringify();

//在参数中指定要转换的其他数据表也是可以的
var str = csv.stringify(csvTable);

//输出到控制台
console.dump(str);
console.more();

//读取 CSV 文件
var csvTable = csv.load("/utf8.csv")

//输出 JSON 到控制台
console.dumpJson(csvTable);

//逐行读取并解�?CSV 文件为列数组�?for tab in csv.each("/utf8.csv") {
    console.dumpTable(tab);
}
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/csv/string.database.md)

