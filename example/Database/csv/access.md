[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: SQL 读写 CSV

```aardio aardio
//SQL 读写 CSV
//下面的代码仅使用系统组件,不需要安�?Access 软件
import access;
import console;

var txt = /*
Name,Starred,Contact_Id
"孟轲","0",0
"张九�?,"1",1
*/

//创建测试的TXT数据库，access 读写�?CSV 必须�?ANSI 编码�?string.save("/Contact.csv",string.fromto(txt) );

//指定 CSV 分隔�?不是默认的逗号就要在这里改
import fsys.ini;
var schema = fsys.ini("/schema.ini");
schema.write("Contact.csv","Format","Delimited(,)");

//创建 CSV 数据库，参数指定 CSV 文件所在目录就可以�?var csv = access( "/" );

//查询并遍历数�?for(rs in csv.each("SELECT * FROM [Contact.csv] " ) ){
     console.log( rs("Name").value,rs("Starred").value    );
}

//关闭 CSV 数据�?csv.close();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/csv/access.md)

