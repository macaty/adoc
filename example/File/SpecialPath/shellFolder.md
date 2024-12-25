[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 打开系统隐藏目录

```aardio aardio
//打开隐藏目录
import win.ui;
/*DSG{{*/
var winform = win.form(text="打开系统隐藏目录";right=759;bottom=469)
winform.add(
edit={cls="edit";left=7;top=10;right=752;bottom=431;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(h=-13);hscroll=1;multiline=1;vscroll=1;z=1};
static={cls="static";text="系统有一些特殊的隐藏目录，可以调用上面的 aardio 代码直接打开�?;left=13;top=440;right=436;bottom=465;db=1;dl=1;dr=1;transparent=1;z=2}
)
/*}}*/

import win.reg;
var reg = win.regReader("HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\FolderDescriptions");
var items  = reg.queryTable("Name","RelativePath");
reg.close();

winform.edit.print('import fsys.knownFolder;')
for(k,item in items){
    winform.edit.printf(`raw.explore("shell:%s"); //fsys.knownFolder("%s")`,item.Name,k)
}

var reg = win.regReader("HKEY_CLASSES_ROOT\CLSID\");
for(clsid,writetime in reg.eachKey() ){
    var subKey = reg.open(clsid,true);
    if(subKey){
        var shellKey = subKey.open("ShellFolder",true)
        if(shellKey){
            var name = subKey.queryValue("");
            if(name) winform.edit.printf(`raw.explore("shell:::%s"); //%s`,clsid,name);
            else winform.edit.printf(`raw.explore("shell:::%s");`,clsid);
            shellKey.close();
        }
        subKey.close();
    }
}
reg.close();

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/SpecialPath/shellFolder.md)

