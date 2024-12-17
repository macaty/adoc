[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlServer �?- MSSQL 增、删、改、查

```aardio aardio
//sqlServer �?-  MSSQL 增、删、改、查

import console;
import sqlServer;

//打开数据�?var db = sqlServer(
    ["Data Source"] = "127.0.0.1,7788"; //"IP地址,服务端口"
    ["Database"]= "database";  //数据库名
    ["User ID"]  = "sa"; //用户�?    ["Password"]= "123456"; //用户密码
)

//创建�?if(!db.existsTable("TestDb109") ){
    //要特别注�?varchar �?ANSI 编码字符串，NVARCHAR �?UTF-16 编码字符串（ aardio 中的 ustring �?    db.exec("create table TestDb109 (url varchar(130), comment NVARCHAR(280), photo binary(200) NULL)")
}

//使用命令参数 - 参数化可避免SQL注入
var cmd = db.createCommand( "INSERT INTO TestDb109(url,comment,photo) VALUES(@url,@comment,@photo)" );

//绑定命令参数,二进制字段只能用这种方法插入
cmd.bind(
    url = "http://bbs.aardio.com"; //UTF-8字符串会�?MSSQL 转换�?ANSI 字符串，这里也可以直接传 buffer�?    comment = '�?�?�?Unicode 字符百科测试一下hi!'u; //NVARCHAR 必须使用 UTF-16 字符串（ustring），其他编码可以�?string.toUtf16() 函数转换为UTF-16 编码�?    photo = raw.buffer("Buffer") //二进制数据，也可�?string.loadBuffer() 加载文件
)

//执行命令
cmd.execute();

//�?- 调用 access.formatParameter() 格式化命名参数生成SQL语句
db.exec( "INSERT INTO TestDb109(url,comment) VALUES(@url,@comment)",{
    url = "http://bbs.aardio.com";
    comment = "字符串包�?单引�? 测试一�?;
} )

//�?db.exec("UPDATE TestDb109 SET url='%s' WHERE comment='%s' ","http://www.aardio.com","这是说明")

//�?for(rs in db.each("SELECT * FROM TestDb109") ){
    console.log( rs("url").value,rs("comment").value,rs("photo").value )
}

//将查询结果转换为普通数�?var tab = db.getTable("SELECT * FROM TestDb109");
console.dump(tab);

//�?- 自动调用 string.format() 函数格式化SQL语句,简单拼接字符串应避免包含单引号
db.exec("DELETE FROM TestDb109 WHERE url='%s'","http://www.aardio.com");

db.exec("DROP TABLE TestDb109")

//关闭数据库连�?db.close();

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/mssql/crud.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/mssql/crud.md')

