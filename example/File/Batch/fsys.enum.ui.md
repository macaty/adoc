[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 閬嶅巻鏂囦欢+鐣岄潰

```aardio aardio
//閬嶅巻鏂囦欢+鐣岄潰
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="閬嶅巻鏂囦欢";right=634;bottom=502;acceptfiles=1)
winform.add(
btnEnum={cls="button";text="閬嶅巻鐩綍";left=310;top=451;right=516;bottom=489;db=1;dl=1;dr=1;z=6};
btnOpenDir={cls="plus";text="閫夋嫨鐩綍";left=478;top=39;right=596;bottom=69;align="left";color=3947580;dr=1;dt=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF07C';notify=1;textPadding={left=25};z=8};
chkSubDir={cls="checkbox";text="閫掑綊澶勭悊瀛愮洰褰?;left=325;top=88;right=441;bottom=104;checked=1;dr=1;dt=1;z=7};
editLog={cls="edit";left=41;top=123;right=588;bottom=434;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=5};
lbDir={cls="static";text="鍙嫋鍔ㄧ洰褰曟湰绋嬪簭涓?";left=41;top=17;right=206;bottom=36;dl=1;dt=1;transparent=1;z=2};
lbExt={cls="static";text="鍚庣紑鍚?";left=47;top=88;right=112;bottom=107;align="right";dl=1;dt=1;transparent=1;z=4};
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
                 winform.editLog.print("鏂囦欢",path);
            }
            else {
                winform.editLog.print("鐩綍",path);
            }

            if(winform.btnEnum.text != "鍋滄"){
                return false;
            }
        },subDir
    );

    winform.editLog.print("宸插畬鎴?);
}

import fsys;
winform.btnEnum.oncommand = function(id,event){
    if( winform.btnEnum.text = "鍋滄" ){
        winform.btnEnum.text = "閬嶅巻鐩綍";
        return;
    }

    if( ! fsys.isDir( winform.txtDir.text ) ){
        return winform.txtDir.showErrorTip("璇锋寚瀹氭纭殑鐩綍","鏂囦欢鍚嶆壒鐞嗘浛鎹㈢▼搴?)
    }

    winform.btnEnum.text = "鍋滄";
    thread.invoke(enumThread,winform);
}

winform.onDropFiles = function(files){
    winform.txtDir.text =  files[1];
}

import fsys.dlg.dir;
winform.btnOpenDir.oncommand = function(id,event){
    winform.txtDir.text = fsys.dlg.dir(,winform,'璇烽�夋嫨瑕佹壒閲忔敼鍚嶇殑鐩綍')
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Batch/fsys.enum.ui.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Batch/fsys.enum.ui.md')

