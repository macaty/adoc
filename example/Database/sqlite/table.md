[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 存取表对�?
```aardio aardio
//sqlite �?- 存取表对�?import sqlite
import console;

//创建测试数据�?var db = sqlite("/tableParameter.db")
if( not db.existsTable("dataTable") ) {
    db.exec( "CREATE TABLE dataTable( name TEXT PRIMARY KEY,info BLOB);" );//指定 name 字段为主�?}

//�?REPLACE 语句添加数据,如果存在相同主键数据则覆�?var cmd = db.prepare("REPLACE INTO [dataTable] VALUES ( @name,@info );")

/*
注意�?sqlite.format() 函数中，参数如果是表通常会被格式化为 SQL 语句�?而在预处理命令中，一个参数值如果是表对象，aardio 会直接将其作�?aardio 表存储到 SQLite�?
下面执行批处理命令，利用 @info 参数值存入了一�?aardio 表对象�?*/
cmd.step(
    name = "相同名称";
    info = {
        a = 123;
        b = {
            d = "测试";
        }
    }
);

cmd.step(
    name = "不同名称";
    info = {
        a = 456;
        b = {
            d = "测试2";
        }
    }
);

/*
查询数据, prepare 的第二个参数如果是表�?表中的名值对会自动生成为 WHERE 条件语句,多个条件会使�?AND 连接�?*/
cmd.prepare("SELECT * FROM [dataTable] ",{
    name = "不同名称"; //可使用键值对指定查询条件
} )

//上面的代码实际会被解析为下面的代�?cmd.prepare("SELECT * FROM [dataTable] WHERE ??",{ {
    name = "不同名称"; //可使用键值对指定查询条件
} } )

console.log("自动生成�?SQL 语句",cmd.sql );
console.more();

var result = cmd.stepQuery(); //执行查询
console.dumpJson(result); //显示查询结果

cmd.finalize();//释放预处理语�?console.more();

//查询数据 返回所有符合条件的行记录数�?//-----------------------------------------------
var dataTable = db.getTable("SELECT * FROM [dataTable] ")
console.dumpJson(dataTable);

//-----------------------------------------------
db.exec("DROP TABLE dataTable "); //删除�?db.close(); //关闭数据�?
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/table.md)

