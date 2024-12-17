[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: BT 涓嬭浇 / Web

```aardio aardio
//BT 涓嬭浇 / Web
import win.ui;
/*DSG{{*/
var winform = win.form(text="aria涓嬭浇鍣?;right=1010;bottom=607;border="none";)
winform.add(
bk={cls="bk";left=0;top=0;right=1012;bottom=31;bgcolor=11841964;dl=1;dr=1;dt=1;forecolor=5392444;linearGradient=0;z=2;};
custom={cls="custom";text="鑷畾涔夋帶浠?;left=0;top=30;right=1012;bottom=609;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=1;};

)
/*}}*/

//鍚姩 aria2
import process.aria2;
var aria2 = process.aria2();
aria2.startServer( maxConcurrentDownloads = 10 );

//瀵煎叆缃戦〉鍓嶇
import web.ariaNg;

//鎵撳紑缃戦〉
import web.view;
var wb = web.view(winform.custom);
wb.go( web.ariaNg.defaultUrl );

//鑷粯鏍囬鏍忋�侀槾褰辫竟妗?import win.ui.simpleWindow;
win.ui.simpleWindow(winform);

//鏀寔鎷栨斁 torrent 鎴?aria2 鏂囦欢鍒涘缓鎴栨仮澶嶄笅杞?wb.onNewWindow = function(url){

    //濡傛灉鎵撳紑鐨勬槸 file: 鍓嶇紑缃戝潃銆?    var filePath = inet.url.getFilePath(url)
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Transfer/bt.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Transfer/bt.md')

