[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: spyHtml

```aardio aardio
import win;
import process;
spyHtml = function(hwnd){
   var outerHtml
   var tid,pid = win.getThreadProcessId(hwnd)
   try{
        //鎵撳紑杩涚▼
        var prcs = process(pid)

        //澹版槑澶栭儴EXE涓殑API鍑芥暟
        var HTMLayoutGetRootElement = prcs.remoteApi("int(int hwnd, pointer& phe)","htmlayout.dll","HTMLayoutGetRootElement" )
        var HTMLayoutGetElementHtml = prcs.remoteApi("int(POINTER he,pointer& utf8bytes,bool outer)","htmlayout.dll","HTMLayoutGetElementHtml" )
        var lstrlen = prcs.remoteApi("int(pointer lpStr)","Kernel32.dll","lstrlen" )

        //璋冪敤澶栭儴EXE涓殑鍑芥暟
        var ok,he = HTMLayoutGetRootElement(hwnd)
        var ok,pHtml = HTMLayoutGetElementHtml(he,,true);
        var size = lstrlen(pHtml) ;

        //杞崲UTF8缂栫爜
        outerHtml = prcs.readString(tonumber(pHtml),size);
        outerHtml = string.fromto( outerHtml );
   }
   return  outerHtml;
}

io.open()
import winex;

//閬嶅巻鎵�鏈夋闈笂浣跨敤浜咹TMLayout鐨勭獥鍙? aardio绐楀彛绂佹鎶撳彇 )
for hwnd,title,threadId,processId in winex.each(  ) {
    try{
        var html = spyHtml( 绐楀彛鍙ユ焺 )
        if( html ){
            io.print( html );
        }
    }
}

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/spyHtml.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/spyHtml.md')

