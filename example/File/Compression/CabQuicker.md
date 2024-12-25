[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: CabQuicker - 压缩打包工具

```aardio aardio
//Cab 打包压缩
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="CabQuicker -  压缩打包工具";right=599;bottom=399;parent=...)
winform.add(
tab={cls="tab";left=9;top=8;right=587;bottom=389;db=1;dl=1;dr=1;dt=1;edge=1;z=1}
)
/*}}*/

var frmCompress,frmUnCompress;

/*压缩工具{{*/
frmCompress = winform.tab.add( text="压缩";acceptfiles=1;bottom=363;parent=...;right=590 )
frmCompress.add(
editDst={ dl=1;bottom=147;right=344;left=41;dt=1;top=120;z=3;text="/test.cab";edge=1;cls="edit" };
btnCompress={ dr=1;bottom=345;text="生成压缩文件";font=LOGFONT(name='FontAwesome');left=393;top=305;z=8;db=1;right=553;cls="button" };
static={ dl=1;bottom=48;right=309;left=41;dt=1;top=26;transparent=1;text="请拖放需要压缩的目录或文件到下面输入框中";z=2;cls="static" };
staticDst={ dl=1;bottom=118;right=309;left=41;dt=1;top=96;transparent=1;text="请选择cab文件存储路径";z=5;cls="static" };
cmbType={ dr=1;bottom=334;right=377;left=314;text="LZX";
items={ "LZX";"MSZIP" };top=314;z=7;db=1;mode="dropdown";edge=1;cls="combobox" };
staticType={ dr=1;bottom=339;align="right";text="压缩算法:";left=238;top=317;z=6;db=1;right=309;transparent=1;cls="static" };
editSrc={ dl=1;bottom=77;right=549;left=41;dt=1;top=48;z=1;edge=1;cls="edit" };
btnBrowser={ dl=1;bottom=149;right=465;left=349;dt=1;top=116;z=4;text="浏览...";cls="button" };
editLog={ dr=1;dl=1;bottom=289;vscroll=1;right=550;left=38;multiline=1;top=171;dt=1;z=9;db=1;hscroll=1;edge=1;cls="richedit" }
)

frmCompress.btnCompress.oncommand = function(id,event){
    frmCompress.btnCompress.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}

    thread.invokeAndWait(
        function(frmCompress,path,target,compressType){
            import win.ui;
            import fsys.cab.maker;
            import console;

            frmCompress.editLog.text = "正在计算文件数目......"
            fsys.cab.maker.logger = frmCompress.editLog;
            ok,err = fsys.cab.maker.compress(path,target,compressType)
            if(ok){
                frmCompress.editLog.appendText(  '\r\n已生�?
                    , err , '\r\n全部操作已完成\r\n'
                );
            }
            else {
                frmCompress.editLog.appendText( '\r\n' , err );
            }
        },frmCompress,frmCompress.editSrc.text,frmCompress.editDst.text
        /*,frmCompress.cmbType.text*/
    )

    frmCompress.btnCompress.disabledText = null;
}
import fsys.dlg;
frmCompress.btnBrowser.oncommand = function(id,event){
    frmCompress.editDst.text = fsys.dlg.save( "*.cab|*.cab||","请选择cab文件存储目录",,frmCompress.hwnd)
}
frmCompress.wndproc = function(hwnd,message,wParam,lParam){
    select(message) {//判断消息类型
        case 0x233/*_WM_DROPFILES*/ {
            var path = win.getDropFile(wParam )[1];
            if( ..string.endWith(path,".cab",true) ){
                frmUnCompress.editSrc.text = path;
                winform.tab.selIndex = 2;
                return;
            }

            frmCompress.editSrc.text = path
            var tPath =  io.splitpath(frmCompress.editSrc.text)

            if( fsys.isDir(frmCompress.editSrc.text) ){
                frmCompress.editDst.text = tPath.dir + tPath.file + ".cab"
            }
            else {
                frmCompress.editDst.text = tPath.dir + tPath.name + ".cab"
            }

            frmUnCompress.editSrc.text = frmCompress.editDst.text;
        }
    }
}
/*}}*/

/*解压缩工具{{*/
frmUnCompress = winform.tab.add(text="解压�?;right=590;bottom=363;acceptfiles=1;parent=...)
frmUnCompress.add(
btnBrowser={cls="button";text="浏览...";left=406;top=117;right=522;bottom=150;dl=1;dt=1;z=4};
btnUnCompress={cls="button";text="解压缩文�?;font=LOGFONT(name='FontAwesome');left=320;top=309;right=480;bottom=349;dl=1;dt=1;z=6};
editDst={cls="edit";text="/";left=41;top=120;right=381;bottom=147;dl=1;dt=1;edge=1;z=3};
editLog={cls="richedit";left=40;top=160;right=566;bottom=301;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=7};
editSrc={cls="edit";left=40;top=48;right=566;bottom=77;dl=1;dt=1;edge=1;z=1};
static={cls="static";text="请拖放需要解压的cab文件到下面输入框�?;left=41;top=26;right=309;bottom=48;dl=1;dt=1;transparent=1;z=2};
staticDst={cls="static";text="请选择存储目录";left=41;top=96;right=309;bottom=118;dl=1;dt=1;transparent=1;z=5}
)

frmUnCompress.onFileInCabinet = function(filename,targetDir,fullTargetName){
    frmUnCompress.editLog.log("正在解压:",filename,'\n');
}

frmUnCompress.btnUnCompress.oncommand = function(id,event){
    frmUnCompress.btnUnCompress.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}

    thread.invokeAndWait(
        function( frmUnCompress,path,target ){
            import fsys.cab;
            fsys.cab.onFileInCabinet = function(...){
                frmUnCompress.onFileInCabinet(...)
            };
            fsys.cab.extract(path,target)
            frmCompress.editLog.log("操作已完�?);
        },frmUnCompress,frmUnCompress.editSrc.text,frmUnCompress.editDst.text
    )

    frmUnCompress.btnUnCompress.disabledText  = null;
}

import fsys.dlg.dir;
frmUnCompress.btnBrowser.oncommand = function(id,event){
    frmUnCompress.editDst.text = import fsys.dlg.dir( frmUnCompress.editDst.text,frmUnCompress.hwnd )
}

frmUnCompress.wndproc = function(hwnd,message,wParam,lParam){
    select(message) {//判断消息类型
        case 0x233/*_WM_DROPFILES*/ {
            var path = win.getDropFile(wParam )[1];
            if( !..string.endWith(path,".cab",true) ){
                frmCompress.editSrc.text = path;
                winform.tab.selIndex = 1;
                return;
            }

            frmUnCompress.editSrc.text = path;
            var tPath =  io.splitpath(frmUnCompress.editSrc.text)
            frmUnCompress.editDst.text = tPath.dir + tPath.name
        }
    }
}

/*}}*/

winform.enableDpiScaling();
winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Compression/CabQuicker.md)

