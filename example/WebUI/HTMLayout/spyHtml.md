[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: spyHtml

```aardio aardio
import win;
import process;
spyHtml = function(hwnd){
   var outerHtml
   var tid,pid = win.getThreadProcessId(hwnd)
   try{
        //打开进程
        var prcs = process(pid)

        //声明外部EXE中的API函数
        var HTMLayoutGetRootElement = prcs.remoteApi("int(int hwnd, pointer& phe)","htmlayout.dll","HTMLayoutGetRootElement" )
        var HTMLayoutGetElementHtml = prcs.remoteApi("int(POINTER he,pointer& utf8bytes,bool outer)","htmlayout.dll","HTMLayoutGetElementHtml" )
        var lstrlen = prcs.remoteApi("int(pointer lpStr)","Kernel32.dll","lstrlen" )

        //调用外部EXE中的函数
        var ok,he = HTMLayoutGetRootElement(hwnd)
        var ok,pHtml = HTMLayoutGetElementHtml(he,,true);
        var size = lstrlen(pHtml) ;

        //转换UTF8编码
        outerHtml = prcs.readString(tonumber(pHtml),size);
        outerHtml = string.fromto( outerHtml );
   }
   return  outerHtml;
}

io.open()
import winex;

//遍历所有桌面上使用了HTMLayout的窗�? aardio窗口禁止抓取 )
for hwnd,title,threadId,processId in winex.each(  ) {
    try{
        var html = spyHtml( 窗口句柄 )
        if( html ){
            io.print( html );
        }
    }
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/spyHtml.md)

