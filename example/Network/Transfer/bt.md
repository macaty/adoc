[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: BT 下载 / Web

```aardio aardio
//BT 下载 / Web
import win.ui;
/*DSG{{*/
var winform = win.form(text="aria下载�?;right=1010;bottom=607;border="none";)
winform.add(
bk={cls="bk";left=0;top=0;right=1012;bottom=31;bgcolor=11841964;dl=1;dr=1;dt=1;forecolor=5392444;linearGradient=0;z=2;};
custom={cls="custom";text="自定义控�?;left=0;top=30;right=1012;bottom=609;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=1;};

)
/*}}*/

//启动 aria2
import process.aria2;
var aria2 = process.aria2();
aria2.startServer( maxConcurrentDownloads = 10 );

//导入网页前端
import web.ariaNg;

//打开网页
import web.view;
var wb = web.view(winform.custom);
wb.go( web.ariaNg.defaultUrl );

//自绘标题栏、阴影边�?import win.ui.simpleWindow;
win.ui.simpleWindow(winform);

//支持拖放 torrent �?aria2 文件创建或恢复下�?wb.onNewWindow = function(url){

    //如果打开的是 file: 前缀网址�?    var filePath = inet.url.getFilePath(url)
    if(filePath){
        if( ..string.endWith(filePath,".torrent",true)
            || ..string.endWith(filePath,".aria2",true)
        ){
            aria2.taskAdd(filePath);
            return true;
        }
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/Transfer/bt.md)

