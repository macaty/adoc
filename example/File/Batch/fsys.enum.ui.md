[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 遍历文件+界面

```aardio aardio
//遍历文件+界面
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="遍历文件";right=634;bottom=502;acceptfiles=1)
winform.add(
btnEnum={cls="button";text="遍历目录";left=310;top=451;right=516;bottom=489;db=1;dl=1;dr=1;z=6};
btnOpenDir={cls="plus";text="选择目录";left=478;top=39;right=596;bottom=69;align="left";color=3947580;dr=1;dt=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF07C';notify=1;textPadding={left=25};z=8};
chkSubDir={cls="checkbox";text="递归处理子目�?;left=325;top=88;right=441;bottom=104;checked=1;dr=1;dt=1;z=7};
editLog={cls="edit";left=41;top=123;right=588;bottom=434;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=5};
lbDir={cls="static";text="可拖动目录本程序�?";left=41;top=17;right=206;bottom=36;dl=1;dt=1;transparent=1;z=2};
lbExt={cls="static";text="后缀�?";left=47;top=88;right=112;bottom=107;align="right";dl=1;dt=1;transparent=1;z=4};
txtDir={cls="edit";left=40;top=43;right=476;bottom=72;dl=1;dr=1;dt=1;edge=1;z=1};
txtExt={cls="edit";text="*.*|*.txt";left=122;top=83;right=302;bottom=112;dl=1;dt=1;edge=1;multiline=1;z=3}
)
/*}}*/

var enumThread = function(winform){

    import fsys;

    var root = winform.txtDir.text;
    var pattern = string.split(winform.txtExt.text,"|");
    var subDir = winform.chkSubDir.checked;

    fsys.enum( root,pattern,
        function(dirname,filename,fullpath,findData){
            var path = fsys.path.relative(fullpath,root,false);

            if(filename){
                 winform.editLog.print("文件",path);
            }
            else {
                winform.editLog.print("目录",path);
            }

            if(winform.btnEnum.text != "停止"){
                return false;
            }
        },subDir
    );

    winform.editLog.print("已完�?);
}

import fsys;
winform.btnEnum.oncommand = function(id,event){
    if( winform.btnEnum.text = "停止" ){
        winform.btnEnum.text = "遍历目录";
        return;
    }

    if( ! fsys.isDir( winform.txtDir.text ) ){
        return winform.txtDir.showErrorTip("请指定正确的目录","文件名批理替换程�?)
    }

    winform.btnEnum.text = "停止";
    thread.invoke(enumThread,winform);
}

winform.onDropFiles = function(files){
    winform.txtDir.text =  files[1];
}

import fsys.dlg.dir;
winform.btnOpenDir.oncommand = function(id,event){
    winform.txtDir.text = fsys.dlg.dir(,winform,'请选择要批量改名的目录')
}
winform.btnOpenDir.skin({
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Batch/fsys.enum.ui.md)

