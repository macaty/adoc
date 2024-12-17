[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏂囦欢鍚嶆壒鐞嗘浛鎹㈢▼搴?
```aardio aardio
//鎵归噺閲嶅懡鍚?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="鏂囦欢鍚嶆壒鐞嗘浛鎹㈢▼搴?;right=619;bottom=381;acceptfiles=1)
winform.add(
btnOpenDir={cls="plus";text="閫夋嫨鐩綍";left=482;top=42;right=600;bottom=72;align="left";color=3947580;dr=1;dt=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF07C';notify=1;textPadding={left=25};z=12};
btnReplace={cls="button";text="寮�濮嬫浛鎹㈡枃浠跺悕";left=155;top=329;right=361;bottom=367;db=1;dr=1;z=9};
chkSubDir={cls="checkbox";text="閫掑綊澶勭悊瀛愮洰褰?;left=156;top=281;right=272;bottom=297;checked=1;db=1;dr=1;z=10};
lbDir={cls="static";text="鍙嫋鍔ㄧ洰褰曟湰绋嬪簭涓?";left=41;top=18;right=206;bottom=37;dl=1;dt=1;transparent=1;z=2};
lbExt={cls="static";text="鍚庣紑鍚?";left=39;top=83;right=146;bottom=102;align="right";dl=1;dt=1;transparent=1;z=7};
lbPattern={cls="static";text="鏂囦欢鍚嶆ā寮忓尮閰嶈鍒?";left=6;top=117;right=146;bottom=136;align="right";dl=1;dt=1;transparent=1;z=4};
lbReplace={cls="static";text="鏇挎崲鍑芥暟:";left=42;top=159;right=149;bottom=182;align="right";dl=1;dt=1;transparent=1;z=5};
progress={cls="progress";left=156;top=308;right=536;bottom=318;db=1;dr=1;edge=1;hide=1;max=100;min=0;z=11};
txtDir={cls="edit";left=40;top=44;right=476;bottom=73;dl=1;dr=1;dt=1;edge=1;z=1};
txtExt={cls="edit";text="*.jpg|*.bmp";left=156;top=78;right=336;bottom=107;dl=1;dt=1;edge=1;multiline=1;z=6};
txtPattern={cls="edit";text="(\a+)(\d+)(\.\w+)";left=156;top=112;right=336;bottom=141;dl=1;dt=1;edge=1;multiline=1;z=3};
txtReplace={cls="edit";left=155;top=151;right=536;bottom=272;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=8}
)
/*}}*/

winform.txtReplace.text = /**
//鍙傛暟璇峰湪涓婇潰鐨勬ā寮忓尮閰嶄腑鐢ㄥ渾鎷彿鎸囧畾
function($1,$2,$3) {
    return $1 ++ string.format("%06d",tonumber($2,10) )
        ++ $3;
}
**/

import fsys;
winform.btnReplace.oncommand = function(id,event){
    if( ! fsys.isDir( winform.txtDir.text ) ){
        return winform.txtDir.showErrorTip("璇锋寚瀹氭纭殑鐩綍","鏂囦欢鍚嶆壒鐞嗘浛鎹㈢▼搴?);
    }

    winform.progress.hide = false;
    winform.btnReplace.disabled = true;

    var files = {};
    var callback = eval(winform.txtReplace.text)

    var pattern = winform.txtPattern.text;
    fsys.enum( winform.txtDir.text , string.split(winform.txtExt.text,"|"),
        function(dir,filename,fullpath,findData){
            if(filename){
                files[fullpath] = io.joinpath( dir,string.replace( filename,pattern,callback), )
                winform.progress.stepIt()
            }
        },winform.chkSubDir.checked
    );

    for( p,np in files){
        winform.progress.stepIt()
        fsys.rename( p,np);
    }

    winform.progress.hide = true;
    winform.btnReplace.disabled = false;
}

winform.onDropFiles = function(files){
    winform.txtDir.text = files[1];
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Batch/rename.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Batch/rename.md')

