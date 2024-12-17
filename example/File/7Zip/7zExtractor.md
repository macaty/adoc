[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 7Zip 瑙ｅ帇缂╂紨绀?
```aardio aardio
//瑙ｅ帇缂?import win.ui;
/*DSG{{*/
var winform = win.form(text="7Zip 瑙ｅ帇缂╂紨绀?;right=774;bottom=437)
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

if( !archive.open( fsys.dlg.open("7z鍘嬬缉鍖厊*.7z||") ) ){
    return winform.msgErr("鎵撳紑鍘嬬缉鍖呭嚭閿?);
}

//鍒楀嚭鎵�鏈夋枃浠?for path,isDir,time,size64 in archive.each(){
    winform.edit.print(path,isDir,time,size64.format())
}

archive.extractSetTotal = function(size){
    winform.edit.print("鍘嬬缉鍖呭ぇ灏?,fsys.formatSize(size) )
}

archive.extractSetCompleted = function(lowSize,hiSize,percent){
    winform.edit.print("宸茶В鍘?,fsys.formatSize(lowSize,hiSize)," %" + percent )
    winform.progress.progressPercentage = percent;
}

archive.extractPrepareOperation = function(askExtractMode,itemIndex,filepath,isDir){
   winform.edit.print("姝ｅ湪瑙ｅ帇",filepath)
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
if( archive.extract( fsys.dlg.dir(,,"璇锋寚瀹氳В鍘嬬洰褰?) ) ){
    winform.edit.print("宸插畬鎴愭墍鏈夋搷浣?)
}
else {
    winform.edit.print("瑙ｅ帇缂╅亣鍒伴敊璇?)
}

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zExtractor.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zExtractor.md')

