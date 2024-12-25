[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: access �?- SQL 操作 Excel

```aardio aardio
//access �?- SQL 操作 Excel
import access;//仅使用系统组�?不需要安�?Access / Excel
//import access.oleDb; //导入此库支持 *.xlsx ，可按需安装 Microsoft.Ace.OLEDB.16 驱动�?
//可自动创建文件，系统自带驱动可支�?*.xls 文件 Excel 8.0( 97-2003 )  格式�?var db,err = access( "/test.xls")

/*
//默认自动配置连接参数，但也可以如下显式指定参�?var db,err = access( "/test.xlsx",
    {
        ["Provider"] = "Microsoft.Ace.OLEDB.16.0";
        ["Extended Properties"] = "Excel 12.0 Xml;HDR=YES"; //XML 格式版本只有 12.0，不存在 16.0
    }
)

关于列数据类型不统一时值丢失或字符串被截断,或使�?Excel 源的其他问题,可参考以下链接：
https://learn.microsoft.com/zh-cn/sql/integration-services/data-flow/excel-source?view=sql-server-ver16
http://www.connectionstrings.com/excel/
*/

//创建�?if( ! db.existsTable( "sheet1" ) ){
    db.exec("CREATE TABLE sheet1 (username VARCHAR(255),comment MEMO,num double )");
}

//插入数据,注意访问excel里的表名后面�?并用放到方括号里
db.exec( "INSERT INTO [sheet1$](username,comment,num)values('aardio','www.aardio.com',123)");

//查询
import console;
for(rs in db.each("SELECT * FROM [sheet1$]") ){
    console.log( rs("username").value );
    console.log( rs("comment").value );
    console.log( rs("num").value )
}

//关闭数据�?db.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/excel/sql.md)

