[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: access 搴?- 铏氳〃

```aardio aardio
//access 搴?- 铏氳〃
//鐩稿叧鑼冧緥锛氳寖渚?/ Windows 绐楀彛 / 鍒楄〃瑙嗗浘鎺т欢 / 铏氳〃
//涓嬮潰listview 鎺т欢鐨勭被鍚嶏紙cls灞炴�э級璇锋敼涓?"vlistview"
import win.ui;
/*DSG{{*/
winform = win.form(text="铏氳〃";right=805;bottom=610)
winform.add(
listview={cls="vlistview";left=27;top=17;right=778;bottom=564;db=1;dl=1;dr=1;dt=1;edge=1;z=1}
)
/*}}*/

winform.listview.insertColumn("缃戝潃", 200);
winform.listview.insertColumn("璇勮", 200);

//鍒涘缓娴嬭瘯鏁版嵁
import access;
var db = access("/test.mdb");
if (!db.existsTable("homepage2")) {
        db.exec("CREATE TABLE homepage2 (url char(30), comment char(20))");

        db.connection.BeginTrans();
        for (i = 1; 1000) {
                db.exec("INSERT INTO homepage2(url, comment) VALUES(@url,@comment)", {
                        url = "http://www.aardio.com";
                        comment = "瀛楃涓插寘鍚?鍗曞紩鍙? " ++ i;
                });
        }
        db.connection.CommitTrans();
}

//鏌ヨ鏁版嵁
var rs = db.openRecordSet("SELECT * FROM homepage2", db.adOpenStatic);

//鎸囧畾铏氳〃琛屾暟
winform.listview.count =  rs.recordCount;

//鏁版嵁搴撶紦瀛樿〃
var cacheTable = table.cache(
    function(row) {
        rs.Move(row - 1, 1/*_adBookmarkFirst*/);

        //娉ㄦ剰杩斿洖鐨勬暟缁勬槸鍏堝垪鍚庤
        return rs.getRows(1,0/*_adBookmarkCurrent*/)
        //return rs.getRows(1,0/*_adBookmarkCurrent*/,{"url","comment"})
    }
);

//鑾峰彇铏氳〃椤?winform.listview.onGetDispItem = function(item,row,col){
    return  {text=cacheTable[row][col][[1]]};
}

winform.listview.onDestroy = function(){
    db.close();
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/access/vlistview.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/access/vlistview.md')

