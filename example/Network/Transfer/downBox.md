[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 涓嬭浇瀵硅瘽妗?
```aardio aardio
//涓嬭浇瀵硅瘽妗?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=425;bottom=110;)
winform.add(
button={cls="button";text="涓嬭浇";left=191;top=38;right=350;bottom=76;z=1}
)
/*}}*/

import inet.downBox;
winform.button.oncommand = function(id,event){
    var downBox = inet.downBox(winform,"涓嬭浇娴嬭瘯缃戦〉...",true )

    var ok = downBox.test( "http://download.aardio.com/v10.files/exlibs/tcc.tar.lzma", "~/download/lib/tcc.tar.lzma" )
    if( ok ){
        winform.msgbox("鏂囦欢宸蹭笅杞藉畬鎴愩�佹湇鍔″櫒鏈洿鏂?鏃犻渶閲嶆柊涓嬭浇")
        return;
    }
    elseif( ok === null ){
        winform.msgboxErr("涓嬭浇閿欒,HTTP閿欒浠ｇ爜:"+ ( downBox.statusCode : ""));
        return;
    }

    if( downBox.download( "http://download.aardio.com/v10.files/exlibs/tcc.tar.lzma" , "~/download/lib/tcc.tar.lzma" ) ){
        //winform.msgbox("download complete");
     }
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Transfer/downBox.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Transfer/downBox.md')

