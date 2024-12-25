[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 请拖动需要监视的目录到下面的文件列表�?
```aardio aardio
//仅监视目�?fsys.watch
import win.ui;
/*DSG{{*/
var winform = ..win.form(text="请拖动需要监视的目录到下面的文件列表�?;right=599;bottom=387;max=false;)
winform.add(
btnWatch={cls="button";text="开始监�?;left=377;top=342;right=529;bottom=379;z=1};
lvChange={cls="listview";left=7;top=6;right=587;bottom=334;acceptfiles=1;bgcolor=16777215;edge=1;z=2}
)
/*}}*/

import fsys.watch;
watchFiles = function( files ){
    var watchObj = fsys.watch( files ) ;
    winform.watchObj = watchObj;

    watchObj.onChange = function(path) {
        var item = winform.lvChange.findItem(path);
        if( item ){
            winform.lvChange.setItemText("改变",item,2);
            winform.lvChange.setItemText(tostring(time.now()),item,3);
        }
    }
    watchObj.run();
}

winform.btnWatch.oncommand = function(id,event){
    if( winform.btnWatch.text == "开始监�?){
        winform.btnWatch.text = "停止监视";
        watchFiles( winform.files);
    }
    else {
        winform.btnWatch.text = "开始监�?;
        winform.watchObj.stop();
    }
}

import fsys;
winform.lvChange.wndproc = {
    [0x233/*_WM_DROPFILES*/] = function(hwnd,message,wParam,lParam){
        var files = win.getDropFile(wParam)
        for(i=1;#files;1){
            if( fsys.isDir(files[i])  )
                winform.lvChange.addItem(files[i])
        }
        winform.files = table.concat(files,winform.files : {} );
    }
}
winform.lvChange.insertColumn("文件",100)
winform.lvChange.insertColumn("状�?,100)
winform.lvChange.insertColumn("时间",200)
winform.lvChange.fillParent(1);

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Monitor/fsys.watch.md)

