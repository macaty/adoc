[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WinAsar - 解包工具

```aardio aardio
import win.ui;
import fonts.fontAwesome;
/*DSG{{*/
var winform = win.form(text="WinAsar - 解包工具";right=1075;bottom=736;acceptfiles=1;bgcolor=16777215;)
winform.add(
btnExtract={cls="plus";text="提取全部文件";left=805;top=666;right=973;bottom=699;align="left";db=1;dr=1;font=LOGFONT(h=-15);notify=1;textPadding={left=35};z=3};
btnOpen={cls="plus";text="选择asar文件";left=623;top=4;right=868;bottom=37;align="left";dr=1;dt=1;font=LOGFONT(h=-15);textPadding={left=35};z=6};
btnReplace={cls="plus";text="保存并替换数�?;left=884;top=4;right=1056;bottom=37;align="left";disabled=1;dr=1;dt=1;font=LOGFONT(h=-15);textPadding={left=35};z=9};
editAsarPath={cls="edit";left=19;top=3;right=617;bottom=40;dl=1;dr=1;dt=1;edge=1;multiline=1;z=5};
editInfo={cls="richedit";left=371;top=42;right=1058;bottom=654;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
editOutDir={cls="edit";left=138;top=666;right=800;bottom=699;acceptfiles=1;db=1;dl=1;dr=1;edge=1;multiline=1;z=7};
progress={cls="plus";left=21;top=710;right=1058;bottom=723;bgcolor=6447459;db=1;dl=1;dr=1;forecolor=9959653;hide=1;z=4};
static={cls="static";text="输出目录:";left=42;top=672;right=128;bottom=696;align="right";db=1;dl=1;font=LOGFONT(h=-15);transparent=1;z=8};
treeview={cls="treeview";left=18;top=43;right=364;bottom=658;asel=false;bgcolor=16777215;db=1;dl=1;dt=1;edge=1;vscroll=1;z=1}
)
/*}}*/

import fsys.asar.reader;
var showAsarInfo = function(){
    var unasar,err = fsys.asar.reader(winform.editAsarPath.text);
    if(!unasar){
        winform.msgboxErr(..string.concat("获取asar文件信息时遇到错�?,err));
        return;
    }

    winform.treeview.clear();
    winform.treeview.insertItem(unasar.treeData());

    winform.editInfo.text = web.json.stringify(unasar.info,true);

    if(winform.unasar) winform.unasar.close();
    winform.unasar = unasar;
    winform.asaPath = winform.editAsarPath.text;

    if( ( !# ( ..string.trim( winform.editOutDir.text )) )
        || (winform.editOutDir.autoPath = winform.editOutDir.text ) ){
        winform.editOutDir.text = winform.asaPath  + ".unpack";
        winform.editOutDir.autoPath = winform.editOutDir.text ;
    }
}

winform.editAsarPath.oncommand = function(id,event){
    if( event == 0x300/*_EN_CHANGE*/){
        if( ..string.endWith(winform.editAsarPath.text,"*.asar")){
                if( ..io.exist(winform.editAsarPath.text)){
                    showAsarInfo();
                };
        }
    }

}

import fsys.dlg;
winform.btnOpen.oncommand = function(id,event){
    var path = fsys.dlg.open("*.asar|*.asar||","请选择asar文件",,winform.hwnd);
    if(#path){
        winform.editAsarPath.text = path;
        showAsarInfo();
    }
}

winform.wndproc = {
    [0x233/*_WM_DROPFILES*/] = function(hwnd,message,wParam,lParam){
        var files = win.getDropFile(wParam)
        if(#files){
             winform.editAsarPath.text = files[1];
             showAsarInfo();
        };
    }
}

winform.editOutDir.wndproc = {
    [0x233/*_WM_DROPFILES*/] = function(hwnd,message,wParam,lParam){
        var files = win.getDropFile(wParam)
        if(#files){
            if( fsys.isDir(files[1]) )
                winform.editOutDir.text = files[1];
        };
    }
}

import fsys;
import win.ui.menu;
import process;
import fsys.mime;
winform.treeview.onnotify = function(id,code,ptr){

    if( code == 0xFFFFFE3D/*_TVN_SELCHANGEDW*/ ){
        var hItem = winform.treeview.getSelection();
        if(hItem){
            var data  = winform.treeview.getItemData(hItem);
            var bin;
            if( data[["size"]]  && data[["size"]] < 0x10000 ){
                bin = winform.unasar.readFile(data.path);
            }

            if( bin && ..string.len( bin )  ){
                 winform.editInfo.text = winform.unasar.readFile(data.path);
                 winform.btnReplace.disabled = false;
            }
            else {
                winform.btnReplace.disabled = true;
                 winform.editInfo.text = web.json.stringify(data,true)
            }

        }
    }
    elseif(code = 0xFFFFFFFB/*_NM_RCLICK*/){ //鼠标右键单击
        var hItem,tvht = winform.treeview.hitTest();
        winform.treeview.setSelected(hItem);
        var data  = winform.treeview.getItemData(hItem);
        if(!data[["size"]]) return;

        var menu = win.ui.popmenu(winform)
        menu.add("Copy To...",
            function(){
                var dir = fsys.getParentDir(winform.asaPath)
                var path = fsys.dlg.save("*.*|*.*||","请选择输出文件",dir ,winform.hwnd,,data.text)

                if(path){

                    var file = io.file(path,"w+b")
                    if(!file) {
                        winform.msgboxErr("Create File Failed!")
                        return;
                    }

                    winform.progress.hide = false;
                    winform.progress.setProgressRange(1,data.size);

                    var buf = raw.buffer(0x100000)
                    for readSize in winform.unasar.eachReadBuffer(buf,data.path) {
                        file.writeBuffer(buf,readSize);
                        winform.progress.progressPos = winform.progress.pos + readSize;
                    }
                    file.close();
                    process.explore(path)
                }
            }
        )
        menu.popup(x,y,true);
    }
}

winform.btnReplace.oncommand = function(id,event){
    hItem = winform.treeview.getSelection();
    var data  = winform.treeview.getItemData(hItem);
    if(!(data[["size"]] && data[["path"]]) ) {
        winform.msgboxErr("Invalid item data");
        return;
    }
    var ret,err  = winform.unasar.replaceText(data[["path"]],winform.editInfo.text)
    if(err) return  winform.msgboxErr(err);

    winform.btnReplace.disabled = true;
    win.delay(1000);
    winform.btnReplace.disabled = false;
}

import fsys.dlg.dir;
import process;
winform.btnExtract.oncommand = function(id,event){
    if(!#winform.asaPath){
        var path = fsys.dlg.open("*.asar|*.asar||","请选择asar文件",,winform.hwnd);
        if(#path){
            winform.editAsarPath.text = path;
            showAsarInfo();
        }
        else {
            return;
        }
    }

    var dir = winform.editOutDir.text;
    var parentDir = fsys.getParentDir(winform.asaPath)
    ..io.createDir(dir)
    if( ! #dir )
        dir = fsys.dlg.dir(parentDir,winform.hwnd,"请选择输出目录");

    if(!dir) return;

    winform.progress.hide = false;
    winform.progress.setProgressRange(1,1000);

    winform.btnExtract.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}
    var msg = MSG()
    for path,size,progress in winform.unasar.eachUnpack(dir) {
        winform.progress.progressPos = progress * 1000;
        win.peekPumpMessage( msg )
    }
    winform.btnExtract.disabledText = null;

    winform.progress.hide = true;
    process.explore_select(dir)
}

winform.btnExtract.skin({
    background={
        default=0xFF8FB2B0;
        hover=0xFF928BB3;
        disabled=0xFFCCCCCC;
    }
})

winform.btnOpen.skin({
    background={
        default=0xFF8FB2B0;
        hover=0xFF928BB3;
        disabled=0xFFCCCCCC;
    }
})

winform.btnReplace.skin({
    background={
        default=0xFF8FB2B0;
        hover=0xFF928BB3;
        disabled=0xFFCCCCCC;
    }
})

winform.show();

win.loopMessage();
return winform;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/asar/forms/extractor.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/asar/forms/extractor.md')
