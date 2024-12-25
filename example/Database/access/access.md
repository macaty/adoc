[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: access �?- mdb 数据�?
```aardio aardio
//access �?- mdb 数据�?//下面的代码仅使用系统组件,不需要安�?Access 软件

import access;
import console;

//打开数据�?如果不存在就自动创建
var db = access("/test.mdb") //也可以直接写数据库连接串 http://www.connectionstrings.com/excel/

//创建�?if(!db.existsTable("aardioTestDb") ){
    /*
    https://docs.microsoft.com/en-us/office/client-developer/access/desktop-database-reference/create-table-statement-microsoft-access-sql
    https://docs.microsoft.com/en-us/office/client-developer/access/desktop-database-reference/sql-data-types
    https://docs.microsoft.com/en-us/office/client-developer/access/desktop-database-reference/equivalent-ansi-sql-data-types
    */
    db.exec("CREATE TABLE aardioTestDb (url CHAR(30), comment CHAR(20), photo IMAGE NULL)")
}

//使用命令参数 - 参数化可避免SQL注入
var cmd = db.createCommand( "INSERT INTO aardioTestDb(url,comment,photo) VALUES(@url,@comment,@photo)" );

//设置所有参数的�?cmd.bind(
    url = "http://www.aardio.com";
    comment = "hi!";
    photo = raw.buffer("Buffer1") //也可�?string.loadBuffer() 加载文件
)

cmd.execute() //执行命令

//�?- 调用 access.formatParameter() 格式化命名参数生成SQL语句
db.exec( "INSERT INTO aardioTestDb(url,comment) VALUES(@url,@comment)",{
    url = "http://www.aardio.com";
    comment = "字符串包�?单引�? 测试一�?;

} )

//�?db.exec("UPDATE aardioTestDb SET url='%s' WHERE comment='%s' ","http://www.aardio.com","这是说明")

//�?for(rs,fields in db.each("SELECT * FROM aardioTestDb") ){
    console.log( rs("url").value,rs("comment").value,rs("photo").value )
}

//将查询结果转换为普通数�?var tab = db.getTable("SELECT * FROM aardioTestDb");
//console.dump(tab);

//�?- 自动调用 string.format() 函数格式化SQL语句,简单拼接字符串应避免包含单引号
db.exec("DELETE * FROM aardioTestDb WHERE url='%s'","http://www.aardio.com");
//注意 access 需要写 delete *, 其他数据库不写星号�?
//关闭数据库连�?db.close();

/*
import access.query;
access.query("/test.mdb");
*/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/access/access.md)

