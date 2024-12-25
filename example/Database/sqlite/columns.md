[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 获取字段�?
```aardio aardio
//sqlite �?- 获取字段�?import console;
import sqlite

var db = sqlite(":memory:");
db.exec( "CREATE TABLE film(title, length, year, starring);")

var cmd = db.prepare("SELECT * FROM [film] ")
var columns = cmd.getColumns();

//显示所有字段名
console.dump(columns);

//获取全部数据�?var dataTable = cmd.getTable();

//这样也可以取到所有字段名
console.dump(dataTable.fields);

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/columns.md)

