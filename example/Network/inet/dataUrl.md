[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Data Url 杞崲宸ュ叿

```aardio aardio
//Data URL 杞崲
import win.ui;
/*DSG{{*/
var winform = win.form(text="Data Url 杞崲宸ュ叿";left=-50;right=399;bottom=325;topmost=1)
winform.add(
edit={cls="edit";left=9;top=9;right=439;bottom=292;acceptfiles=1;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='瀹嬩綋');hscroll=1;multiline=1;vscroll=1;z=1};
static={cls="static";text="璇峰皢鍥剧墖绛夋枃浠舵嫋鏀惧埌涓婇潰鐨勬枃鏈涓繘琛岃浆鎹?;left=11;top=300;right=433;bottom=324;db=1;dl=1;transparent=1;z=2}
)
/*}}*/

import fsys;
import fsys.mime;
winform.edit.wndproc = function(hwnd,message,wParam,lParam){
    if( message == 0x233/*_WM_DROPFILES*/ ){
        if( winform.edit.busy ) return;

        var path = win.getDropFile(wParam)[1]
        if( fsys.isDir(path) ){
            winform.edit.text = "璺緞涓嶈兘鏄竴涓洰褰?
            return;
        }

        var mime = fsys.mime.fromFile( path )
        if(!mime){
            winform.edit.text = "鏃犳晥鐨勬枃浠舵牸寮?;
            return;
        }

        winform.edit.busy = true;
        winform.edit.text = "姝ｅ湪杞崲,璇风◢鍊?.....";
        winform.edit.text = thread.invokeAndWait(function(path,mime){
            import inet.urlData;
            return inet.urlData(,path);
        },path,mime);

        winform.edit.busy = false;
    }
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/inet/dataUrl.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/inet/dataUrl.md')

