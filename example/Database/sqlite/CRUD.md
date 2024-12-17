[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 增删改查

```aardio aardio
//sqlite �?- 增删改查

import sqlite
import console;

var db = sqlite("/test-sqlite.db"); //创建数据�?if( not db.existsTable("film") ){
    db.exec( "CREATE TABLE [film](title, length, year, starring);"); //创建�?}

//�?- 使用命名参数示例
var cmd = db.prepare("REPLACE INTO film VALUES (@title,@length,@year, 'Jodie Foster');" )
cmd.step(
    title = "标题";
    length = 4;
    year = time.now();
)

//�?- 执行SQL语句，支持参数化 SQL，支持数组参�?db.exec("DELETE FROM ?? WHERE title=?;",{ "film","要删除的标题"} )

//�?- exec 函数也可以用一个表参数指定 SQL 命名参数
db.exec("UPDATE film SET title = @title,length=@length WHERE title = @oldTitle;",{
    title = "新的标题123";
    length = #"新的标题";
    oldTitle = "标题";
} );

//�?- 返回首行数据
var result = db.stepQuery("SELECT * FROM [film]"
    /*
    如果 SQL 语句没有指定命名参数�?    则参数可使用表对象中的名值对指定可选的 WHERE 条件参数 —�?多个条件自动添加 AND 连接�?    */
    ,{ title = "新的标题"}
)

//�?- 遍历查询结果
for rowid,title, length, year, starring in db.each("SELECT rowid,* FROM film") {
    /*
    for 语句的第一个返回值如果为 null 就会退出循�?
    如果数据库返回的第一个字段可能为�?那么可以�?SQLite 默认就有的索引字�?rowid 放在最前面
    */
    console.log( rowid,title, length, year, starring  )
}

//删除�?db.exec("DROP TABLE film" );

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/sqlite/CRUD.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/sqlite/CRUD.md')

