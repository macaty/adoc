[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: sqlite �?- 虚表

```aardio aardio
//sqlite �?- 虚表
//相关范例：范�?/ Windows 窗口 / 列表视图控件 / 虚表
//下面listview 控件的类名（cls属性）请改�?"vlistview"
import win.ui;
/*DSG{{*/
winform = win.form(text="虚表";right=805;bottom=610)
winform.add(
listview={cls="vlistview";left=27;top=17;right=778;bottom=564;db=1;dl=1;dr=1;dt=1;edge=1;z=1}
)
/*}}*/

winform.listview.insertColumn("网址", 200);
winform.listview.insertColumn("评论", 200);

//创建测试数据
import sqlite;
var db = sqlite(":memory:")
if (!db.existsTable("homepage2")) {
    db.exec("CREATE TABLE homepage2 (url char(30), comment char(20))");

    db.beginTrans()
    for (i = 1; 100) {
        db.exec("INSERT INTO homepage2(url, comment) VALUES(@url,@comment)", {
            url = "http://www.aau.cn";
            comment = "字符串包�?单引�? " ++ i;
        });
    }
    db.commitTrans()
}

//指定虚表行数
winform.listview.count = db.stepResult("SELECT count(*) FROM homepage2")[1];

//数据库缓存表
var cacheTable = table.cache(
    lambda(row) db.stepResult("SELECT * FROM homepage2 Limit 1 Offset %d",row-1)
);

//获取虚表�?winform.listview.onGetDispItem = lambda(item,row,col){text=cacheTable[row][col]};

winform.listview.onDestroy = function(){
    db.close();
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/sqlite/vlistview.md)

