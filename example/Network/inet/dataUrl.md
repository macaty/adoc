[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Data Url 转换工具

```aardio aardio
//Data URL 转换
import win.ui;
/*DSG{{*/
var winform = win.form(text="Data Url 转换工具";left=-50;right=399;bottom=325;topmost=1)
winform.add(
edit={cls="edit";left=9;top=9;right=439;bottom=292;acceptfiles=1;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='宋体');hscroll=1;multiline=1;vscroll=1;z=1};
static={cls="static";text="请将图片等文件拖放到上面的文本框中进行转�?;left=11;top=300;right=433;bottom=324;db=1;dl=1;transparent=1;z=2}
)
/*}}*/

import fsys;
import fsys.mime;
winform.edit.wndproc = function(hwnd,message,wParam,lParam){
    if( message == 0x233/*_WM_DROPFILES*/ ){
        if( winform.edit.busy ) return;

        var path = win.getDropFile(wParam)[1]
        if( fsys.isDir(path) ){
            winform.edit.text = "路径不能是一个目�?
            return;
        }

        var mime = fsys.mime.fromFile( path )
        if(!mime){
            winform.edit.text = "无效的文件格�?;
            return;
        }

        winform.edit.busy = true;
        winform.edit.text = "正在转换,请稍�?.....";
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/inet/dataUrl.md)

