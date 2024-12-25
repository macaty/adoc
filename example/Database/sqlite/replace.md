[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- replace 语句

```aardio aardio
//sqlite �?- replace 语句
import sqlite;
import console;

//打开内存数据�?var db = sqlite(":memory:");
if( not db.existsTable("tableName2") ){

    //创建单主键表
    db.exec( "CREATE TABLE tableName(title PRIMARY KEY, length, tm);" )

    //创建双主键表
    db.exec( "CREATE TABLE tableName2(title,length,tm,  constraint pk_tableName2 PRIMARY KEY (title,length) );")
}

//replace语句根据主键查询,不存在相同数据则插入新的,否则更新已存在的数据
db.exec( "REPLACE INTO tableName VALUES ('Silence of the Lambs, The', 11.8, datetime('now','localtime')  );")
db.exec( "REPLACE INTO tableName2 VALUES @values;",{
    values  = {
        { 'Contact', 32, time.now() },
        { 'Contact', 16, time.now() }
    }
})

/*
REPLACE INTO 必须要设置所有无默认值字段的�?
如果要在插入冲突时修改部分字�?请用下面的方�?*/
db.exec("
    INSERT OR IGNORE INTO tableName (title,length,tm) VALUES (@title,@length,@tm);
    UPDATE tableName SET tm=@tm WHERE title=@title",{
        title = 'Silence of the Lambs, The';
        length = 123;
        tm = "456"
    } )

for title,length,tm in db.each("SELECT * FROM tableName") {
    console.log( title,length,tm );
}

for title,length,tm in db.each("SELECT * FROM tableName2") {
    console.log( title,length,tm );
}

db.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/replace.md)

