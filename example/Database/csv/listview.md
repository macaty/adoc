[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用 listview 导入导出 CSV 数据

```aardio aardio
//使用 listview 导入导出 CSV 数据
import win.ui;
import string.database;
import fsys.dlg;
/*DSG{{*/
var winform = win.form(text="CSV 导入导出示例";right=759;bottom=469)
winform.add(
btnExport={cls="button";text="导出 CSV";left=597;top=415;right=732;bottom=450;db=1;dr=1;z=3};
btnImport={cls="button";text="导入 CSV";left=25;top=415;right=160;bottom=450;db=1;dl=1;z=2};
listview={cls="listview";left=51;top=23;right=700;bottom=385;edge=1;z=1}
)
/*}}*/

// 导入 CSV 文件�?listview
winform.btnImport.oncommand = function(id,event){
    var path = fsys.dlg.open("CSV 文件|*.csv||","选择要导入的 CSV 文件");
    if(!path) return;

    var db = string.database();
    var data = db.load(path);

    winform.listview.setTable(data)
}

// �?listview 导出�?CSV 文件
winform.btnExport.oncommand = function(id,event){

    var dataTable =  winform.listview.getTable(true);
    var path = fsys.dlg.save("CSV 文件|*.csv||","选择保存位置");
    if(!path) return;

    // 创建 CSV 数据�?    var csv = string.database();

    // 保存 CSV 到文�?    csv.save(path,dataTable);

    winform.msgbox("CSV 文件导出成功�?);
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Database/csv/listview.md)

