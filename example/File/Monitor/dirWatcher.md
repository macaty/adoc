[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐩戣鏂囦欢 fsys.dirWatcher

```aardio aardio
//鐩戣鏂囦欢 fsys.dirWatcher
/*
鐩戣鏂囦欢鐨勬柟娉曟湁寰堝,鏇存帹鑽愬ぇ瀹朵娇鐢ㄧ殑鏄?fsys.dirWatcher
*/

import win.ui;
/*DSG{{*/
var winform = win.form(text="鐩戣鏂囦欢 fsys.dirWatcher";right=599;bottom=399;)
winform.add(
btnWatch={cls="button";text="鐩戣鐩綍";left=354;top=342;right=526;bottom=380;dr=1;dt=1;z=1};
editChange={cls="edit";left=23;top=21;right=564;bottom=322;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2}
)
/*}}*/

import process;
import fsys.dirWatcher;
import fsys.dlg.dir;

//鍚姩鏂囦欢鐩戞帶
winform.btnWatch.oncommand = function(id,event){

    var watchDir = fsys.dlg.dir(,winform.hwnd,"璇烽�夋嫨瑕佺洃瑙嗙殑鐩綍");
    if( watchDir ) {
        winform.btnWatch.disabled = true;

        //鍒涘缓鐩戣绾跨▼
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
    winform.thrdWatcher.close(); //鍋滄鐩戣鏂囦欢
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Monitor/dirWatcher.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Monitor/dirWatcher.md')

