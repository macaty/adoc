[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 提问前必�?
```aardio aardio
//sqlite �?- 提问前必�?import console;

/*
标准�?sqlite 使用�?SQLite.dll 体积较小，但并非最新版�?一般够用，但不支持一�?SQLite.dll 新版才有的功能�?
如果使用 import sqlite.latest 替代 import sqlite�?则会改用新版 SQLite 组件，体积会大一些，但支持的功能更多一些�?*/
import sqlite.latest;
/*
sqlite.latest 会不定期更新 SQLite.dll，但不会频繁更新，也不保证与 SQLite 官方同步�?如果需要更�?SQLite.dll，请参�?sqlite.latest 源码添加对应的库即可�?*/

//其他代码不用变，用的时候还是用 sqlite （不要改�?sqlite.latest �?var db = sqlite(":memory:"); //创建内存数据�?db.exec( "CREATE TABLE [film](title, length, year, starring);"); //创建�?
//查询
var result = db.getTable("SELECT m.name as tableName,
    p.name as columnName FROM sqlite_master m JOIN pragma_table_info((m.name)) p
" )
console.dump(result);

console.log("SQLite 版本",sqlite.version())
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/latest.md)

