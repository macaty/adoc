[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 参数化进�?
```aardio aardio
//sqlite �?- 参数化进�?
/*
一、说�?aardio 中所有数据库的支持库都支持用法与规则类似的参数化语法�?请不要用字符串拼接的方法生成  SQL 语句，这会导致不当字符注�?SQL 语句的意外或风险�?
参数化查询可以避免注入问题�?aardio 在预处理命令使用�?sqlite 原生的参数化查询功能�?也使�?sqlite.format 改进和增强了 SQL 参数化查询的语法�?
sqlite 中执行SQL的函�?sql 语句后面如果是一个表�?就会调用 sqlite.format 使用参数化规则格式化并生成新�?SQL 语句�?如果参数不是一个表，则简单的调用 string.format 函数格式化�?string.format 并不具有参数化、避免注入等功能，应当尽量避免使用�?*/

import console;
import util.table;
import sqlite;

sqlite.format2 = sqlite.format;
sqlite.format = function(sql,...){
    console.log('\r\n格式化代码：')
    console.log("-------------------------------------------------")
    console.log(`sqlite.format("`+sql + `",` + util.table.stringify(...) + `);` );
    console.log('\r\n格式化结果：')
    console.log("-------------------------------------------------")

    sql = sqlite.format2(sql,...)
    console.log(sql);

    console.more(1,true);
    return sql;
}

console.log( "SQL语句�?@ 字符开始的命名参数使用参数表的名值对元素格式�? );
sqlite.format("SELECT *　FROM `tab-name` WHERE name = @name",{name = "参数�?})

console.log( "SQL语句�?? �??? 占位符使用参数表的数组元素格式化" );
sqlite.format("SELECT *　FROM `tab-name` WHERE name = ? AND text = ?",{"参数�?","参数�?"});

console.log( "其中 ?? 格式化为标识�? 放入反引�?),其他占位符格式化为参数�? );
sqlite.format("SELECT *　FROM ?? WHERE name = ? AND text = ?",{"`format-tab`","参数�?","参数�?"});

console.log( "字符串转�?SQL 安全转义字符�?buffer转为X'4D7953514C'格式" );
sqlite.format("SELECT *　FROM ``format-tab`` WHERE str = @str AND buffer = @buffer",{str="a'a";buffer=raw.buffer("sqlite")});

console.log( "数组则自动展开为列�?例如{'a', 'b'}格式化为'a', 'b'" );
sqlite.format("INSERT INTO `format-tab`(??) VALUES(?)",{{'name1', 'name2'},{'value1', 'value2'}});

console.log( "嵌套数组则格式化为分组列�? );
sqlite.format("INSERT INTO `format-tab`(text,number) VALUES @values",{ values = { {'text1', 123}, {'text2', 456} } });

console.log( "非数组的命名表，则格式化�?SQL 键值对,默认以逗号为分隔符" );
sqlite.format("UPDATE `format-tab` SET ?",{ {text="text2";number=123} });

console.log( "??占位符用于格式化 SQL 键值对则以 AND 为分隔符,数组值转换为IN语句" );
sqlite.format("UPDATE `format-tab` SET text=? WHERE ??",{ "text2+",{text="text2";number={1,2,456}} });

sqlite.format = sqlite.format2;
var db = sqlite("/test-sqlite.db");
if( not db.existsTable("format-tab") ){
    db.exec( "CREATE TABLE `format-tab`(text, number);");
}

//执行参数�?SQL 插入数据
db.exec("INSERT INTO `format-tab`(text,number) VALUES @values",{ values = { {'text1', 123}, {'text2', 456} } });

//查询数据
console.dumpJson(db.getTable("SELECT * FROM `format-tab` "))

//删除测试�?db.exec("DROP TABLE [format-tab]" );
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/sqlite.format.md)

