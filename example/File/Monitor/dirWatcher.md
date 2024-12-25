[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 监视文件 fsys.dirWatcher

```aardio aardio
//监视文件 fsys.dirWatcher
/*
监视文件的方法有很多,更推荐大家使用的�?fsys.dirWatcher
*/

import win.ui;
/*DSG{{*/
var winform = win.form(text="监视文件 fsys.dirWatcher";right=599;bottom=399;)
winform.add(
btnWatch={cls="button";text="监视目录";left=354;top=342;right=526;bottom=380;dr=1;dt=1;z=1};
editChange={cls="edit";left=23;top=21;right=564;bottom=322;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2}
)
/*}}*/

import process;
import fsys.dirWatcher;
import fsys.dlg.dir;

//启动文件监控
winform.btnWatch.oncommand = function(id,event){

    var watchDir = fsys.dlg.dir(,winform.hwnd,"请选择要监视的目录");
    if( watchDir ) {
        winform.btnWatch.disabled = true;

        //创建监视线程
        winform.thrdWatcher = fsys.dirWatcher.thread(
            function(filename,action,actionText){
                winform.editChange.appendText( filename," -> ",actionText,'\r\n')
            }, watchDir);

        process.explore( watchDir )
    }
}

import fsys.file;
import thread.event;
winform.onClose = function(hwnd,message,wParam,lParam){
    if(!winform.thrdWatcher) return;
    winform.thrdWatcher.close(); //停止监视文件
}

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Monitor/dirWatcher.md)

