[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 下载对话�?
```aardio aardio
//下载对话�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=425;bottom=110;)
winform.add(
button={cls="button";text="下载";left=191;top=38;right=350;bottom=76;z=1}
)
/*}}*/

import inet.downBox;
winform.button.oncommand = function(id,event){
    var downBox = inet.downBox(winform,"下载测试网页...",true )

    var ok = downBox.test( "http://download.aardio.com/v10.files/exlibs/tcc.tar.lzma", "~/download/lib/tcc.tar.lzma" )
    if( ok ){
        winform.msgbox("文件已下载完成、服务器未更�?无需重新下载")
        return;
    }
    elseif( ok === null ){
        winform.msgboxErr("下载错误,HTTP错误代码:"+ ( downBox.statusCode : ""));
        return;
    }

    if( downBox.download( "http://download.aardio.com/v10.files/exlibs/tcc.tar.lzma" , "~/download/lib/tcc.tar.lzma" ) ){
        //winform.msgbox("download complete");
     }
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Transfer/downBox.md)

