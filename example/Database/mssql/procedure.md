[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlServer �?- MSSQL 存储过程

```aardio aardio
//sqlServer �?-  MSSQL 存储过程

import console;
import sqlServer;

//打开数据�?var db = sqlServer(
    ["Data Source"]= "IP地址,服务端口";
    ["Database"]= "数据库名";
    ["User ID"]  = "用户�?;
    ["Password"]= "用户密码";
)

//创建存储过程
if( ! db.existsProcedure("proc_aardio_test2") ){
    db.exec("
    CREATE PROC proc_aardio_test( @a INT OUTPUT,@b INT )
    AS
    begin
        SET @a=123
        SELECT @a
        SELECT @a + @b
    end
    ");
}

//创建命令参数对象,用于执行存储过程
var cmd = db.createCommand( "proc_aardio_test2" );

//绑定存储过程参数
cmd.bind(
    a = 2;
    b = 3;
)

//执行并显示结�?console.dump(cmd.stepQuery() )

console.dump("输出参数a的�?,cmd.parameters("@a").value)

/*
//多结果集查询示例
var rs = cmd.executeRecords();
var data = rs.stepQuery()

//下一个结果集
rs = rs.nextRecordset();
var data = rs.stepQuery()
*/

//关闭数据库连�?db.close();

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/mssql/procedure.md)

