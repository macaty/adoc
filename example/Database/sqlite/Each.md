[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlie 数据库示�?- 遍历与显示查询结�?
```aardio aardio
//sqlite �?- 遍历与显�?import win.ui;
/*DSG{{*/
var winform = win.form(text="sqlie 数据库示�?- 遍历与显示查询结�?;right=1031;bottom=712)
winform.add(
edit={cls="edit";left=25;top=584;right=997;bottom=693;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
listview={cls="listview";left=24;top=27;right=996;bottom=555;db=1;dl=1;dr=1;dt=1;edge=1;z=1}
)
/*}}*/

//创建测试数据�?import sqlite;
var db = sqlite("/test-sqlite.db");
if( not db.existsTable("each-tab") ){
    db.exec( "CREATE TABLE [each-tab](text, number);");
}

//添加测试数据
var cmd = db.prepare("INSERT INTO [each-tab] VALUES (@text, @number );")
for(i=1;5;1){ cmd.step(number = i;text = "测试数据" + i ) }

//创建迭代器遍历查询结�?for rowid,number,text in db.each("SELECT rowid,number,text FROM [each-tab]") {
    /*
    for 语句的第一个返回值如果为 null 就会退出循�?
    如果数据库返回的第一个字段可能为�?那么可以�?SQLite 默认就有的索引字�?rowid 放在最前面
    */
    winform.edit.print( rowid,number,text )
}

//也可以用 getTable 一次取出所有的数据
var dataTable = db.getTable("SELECT rowid,number,text FROM [each-tab]")

/*
result 是包�?到多条数据的数组�?但也包含 fields 字段用于声明所有列�?
不要 for(k,v in dataTable) { } 这样写，这样会不必要地遍历到 fields
*/
for i,v in table.eachIndex(dataTable){
    //应当使用专门用于遍历数组�?table.eachIndex 创建迭代�?    winform.edit.print(v.rowid,v.number,v.text)
}

import win.ui.grid;
var grid = win.ui.grid(winform.listview);//创建数据视图
grid.setTable( dataTable ) //直接显示数据库的查询结果,视图控件通过 dataTable.fields 获取所有字段名

//删除测试�?db.exec("DROP TABLE [each-tab]" );

winform.show(true);
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/Each.md)

