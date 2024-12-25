[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 特殊文件�?
```aardio aardio
//特殊路径
import fsys;
import fsys.info;
import fsys.environment;
import win.ui;
/*DSG{{*/
var winform = win.form(text="特殊文件�?;right=1071;bottom=815)
winform.add(
btnFind={cls="button";text="查找";left=732;top=755;right=860;bottom=798;db=1;dr=1;z=2};
edit={cls="richedit";left=27;top=11;right=1049;bottom=728;db=1;dl=1;dr=1;dt=1;edge=1;hidesel=false;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

var shell = com.CreateObject("shell.application");
var libPath = io.libpath("fsys")

for csidl,idNumber in fsys.gmatch(libPath,"(_CSIDL_\w+)=@(<0x>?\x+)") {
    idNumber = tonumber(idNumber);
    var path = io.getSpecial(idNumber);
    if(!path) continue;

    winform.edit.printf("io.getSpecial(%s)",csidl);
    winform.edit.print(path);

    var pathWithEnv = fsys.environment.unExpand(path)
    if(pathWithEnv!=path) winform.edit.print(pathWithEnv);

    var folder = shell.NameSpace(path);
    winform.edit.print(fsys.info.get(path,0x200/*_SHGFI_DISPLAYNAME*/)[["szDisplayName"]]);

    winform.edit.print();
}

import win.dlg.findReplace;
var frDlg = win.dlg.findReplace(winform);

frDlg.onSearch = function(findWhat,down,matchCase,wholeWord){
    winform.edit.findText(findWhat,frDlg.flags);
}

winform.btnFind.oncommand = function(id,event){
    frDlg.find(winform.edit.selText)
}

winform.edit.enablePopMenu();

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/SpecialPath/io.getSpecial.md)

