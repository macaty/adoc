[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 浣跨敤 listview 瀵煎叆瀵煎嚭 CSV 鏁版嵁

```aardio aardio
//浣跨敤 listview 瀵煎叆瀵煎嚭 CSV 鏁版嵁
import win.ui;
import string.database;
import fsys.dlg;
/*DSG{{*/
var winform = win.form(text="CSV 瀵煎叆瀵煎嚭绀轰緥";right=759;bottom=469)
winform.add(
btnExport={cls="button";text="瀵煎嚭 CSV";left=597;top=415;right=732;bottom=450;db=1;dr=1;z=3};
btnImport={cls="button";text="瀵煎叆 CSV";left=25;top=415;right=160;bottom=450;db=1;dl=1;z=2};
listview={cls="listview";left=51;top=23;right=700;bottom=385;edge=1;z=1}
)
/*}}*/

// 瀵煎叆 CSV 鏂囦欢鍒?listview
winform.btnImport.oncommand = function(id,event){
    var path = fsys.dlg.open("CSV 鏂囦欢|*.csv||","閫夋嫨瑕佸鍏ョ殑 CSV 鏂囦欢");
    if(!path) return;

    var db = string.database();
    var data = db.load(path);

    winform.listview.setTable(data)
}

// 浠?listview 瀵煎嚭鍒?CSV 鏂囦欢
winform.btnExport.oncommand = function(id,event){

    var dataTable =  winform.listview.getTable(true);
    var path = fsys.dlg.save("CSV 鏂囦欢|*.csv||","閫夋嫨淇濆瓨浣嶇疆");
    if(!path) return;

    // 鍒涘缓 CSV 鏁版嵁搴?    var csv = string.database();

    // 淇濆瓨 CSV 鍒版枃浠?    csv.save(path,dataTable);

    winform.msgbox("CSV 鏂囦欢瀵煎嚭鎴愬姛锛?);
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/csv/listview.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/csv/listview.md')

