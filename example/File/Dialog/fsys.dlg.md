[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 文件对话�?
```aardio aardio
//文件对话�?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="文件对话�?;right=652;bottom=195;bgcolor=16777215;border="dialog frame";max=false;min=false)
winform.add(
btnIFileOpenDir={cls="plus";text="打开目录";left=459;top=49;right=612;bottom=79;align="left";color=3947580;dr=1;dt=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF07C';notify=1;textPadding={left=25};z=3};
btnOpen={cls="button";text="打开文件";left=145;top=120;right=251;bottom=155;db=1;dl=1;z=1};
btnSave={cls="button";text="保存文件";left=270;top=120;right=376;bottom=155;db=1;dl=1;dr=1;z=2};
editPath={cls="plus";left=59;top=49;right=455;bottom=75;align="right";border={bottom=1;color=-6908266};dl=1;dr=1;dt=1;editable=1;font=LOGFONT(h=-13);textPadding={top=6;bottom=2};z=4};
static={cls="static";text="上面�?plus 控件可以在右键菜单中点复制，然后可以粘贴到其他窗�?;left=161;top=92;right=558;bottom=106;color=8421504;transparent=1;z=5}
)
/*}}*/

import fsys.dlg;
winform.btnOpen.oncommand = function(id,event){
    var path = fsys.dlg.open('所有文件|*.*|文本文件|*.txt||',,,winform);
    if(path){
        winform.editPath.text = path;
    }
}

winform.btnSave.oncommand = function(id,event){
    var path = fsys.dlg.save('所有文件|*.*|文本文件|*.txt||',,,winform);
    if(path){
        winform.editPath.text = path;
    }
}

//仅支�?Win7 以及 Win7 以后版本,XP 系统 自动降级�?fsys.dlg.openDir
import fsys.dlg.dir;
winform.btnIFileOpenDir.oncommand = function(id,event){
    var path = fsys.dlg.dir(,winform,'请选择目录')
    if(path){
        winform.editPath.text = path;
    }
}
winform.btnIFileOpenDir.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
})

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Dialog/fsys.dlg.md)

