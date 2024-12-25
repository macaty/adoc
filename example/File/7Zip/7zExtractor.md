[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 7Zip 解压缩演�?
```aardio aardio
//解压�?import win.ui;
/*DSG{{*/
var winform = win.form(text="7Zip 解压缩演�?;right=774;bottom=437)
winform.add(
edit={cls="edit";left=11;top=20;right=763;bottom=388;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1};
progress={cls="plus";left=16;top=410;right=762;bottom=422;bgcolor=6447459;db=1;dl=1;dr=1;forecolor=9959653;notify=1;z=2}
)
/*}}*/

winform.progress.setProgressRange(1,100);
winform.show();

import fsys.dlg;
import sevenZip.decoder2;
import win.dlg.message;

var archive = sevenZip.decoder2();
archive.printError = function(name,message){
    winform.edit.print(name,message);
}

if( !archive.open( fsys.dlg.open("7z压缩包|*.7z||") ) ){
    return winform.msgErr("打开压缩包出�?);
}

//列出所有文�?for path,isDir,time,size64 in archive.each(){
    winform.edit.print(path,isDir,time,size64.format())
}

archive.extractSetTotal = function(size){
    winform.edit.print("压缩包大�?,fsys.formatSize(size) )
}

archive.extractSetCompleted = function(lowSize,hiSize,percent){
    winform.edit.print("已解�?,fsys.formatSize(lowSize,hiSize)," %" + percent )
    winform.progress.progressPercentage = percent;
}

archive.extractPrepareOperation = function(askExtractMode,itemIndex,filepath,isDir){
   winform.edit.print("正在解压",filepath)
}
archive.extractSetOperationResult = function(opRet){
        if( opRet == 0/*kOK*/ ){
            winform.edit.print("OK!")
        }
        elseif( opRet == 1/*kUnSupportedMethod*/ ){
            winform.edit.print("Unsupported Method")
        }
        elseif( opRet == 0/*kDataError*/ ){
            winform.edit.print("CRC Failed")
        }
        elseif( opRet == 0/*kCRCError*/ ){
            winform.edit.print("Data Error")
        }
        else {
           winform.edit.print("Unknown Error")
        }
}

import fsys.dlg.dir;
if( archive.extract( fsys.dlg.dir(,,"请指定解压目�?) ) ){
    winform.edit.print("已完成所有操�?)
}
else {
    winform.edit.print("解压缩遇到错�?)
}

win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zExtractor.md)

