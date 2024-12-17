[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵惧浘浠ｇ爜鐢熸垚鍣?
```aardio aardio
//鎵惧浘浠ｇ爜鐢熸垚鍣?import win.ui;
/*DSG{{*/
var winform = win.form(text="鎵惧浘浠ｇ爜鐢熸垚鍣?;right=454;bottom=403)
winform.add(
btnSnap={cls="button";text="閫夋嫨瑕佹煡鎵剧殑鐩爣鍥惧儚";left=146;top=324;right=450;bottom=400;color=14120960;db=1;dl=1;dr=1;font=LOGFONT(h=-14);note="鍦ㄥ睆骞曚笂妗嗛�夎鏌ユ壘鐨勭洰鏍囧浘鍍忥紝
鐩爣鍥惧儚瓒婂皬锛岀壒寰佽秺鏄庢樉锛屾壘鍥炬晥鏋滆秺濂?;z=3};
btnTest={cls="button";text="杩愯娴嬭瘯";left=325;top=7;right=418;bottom=34;dr=1;dt=1;z=5};
editCode={cls="edit";left=5;top=40;right=443;bottom=319;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
plusImage={cls="plus";left=7;top=337;right=106;bottom=385;db=1;dl=1;repeat="scale";z=1};
static3={cls="static";text="鑷姩鎵惧浘浠ｇ爜锛?;left=8;top=14;right=244;bottom=37;dl=1;dt=1;transparent=1;z=4}
)
/*}}*/

import mouse;
import soImage;
import winex;
winform.btnSnap.oncommand = function(id,event){

    import gdip.snap;
    import mouse.screenArea;
    var screenArea = mouse.screenArea();
    screenArea.onSelectionChanged = function(rc){
        //灏介噺鎴彇鐗瑰緛鏄庢樉鐨勫浘
        var bmp = gdip.snap(screenArea.hwnd,rc);
        var buf = bmp.saveToBuffer("*.jpg",80);
        winform.plusImage.background = buf;
        var strJpg = ..string.escape(buf);

        owner.close();

        var x,y = mouse.getPos();
        winex.waitClose(screenArea.hwnd);

        var hwndTarget = winex.fromPointReal( x,y,0x0004/*_CWP_SKIPTRANSPARENT*/ | 0x0001/*_CWP_SKIPINVISIBLE*/  );
        var hwndRoot = win.getRoot(hwndTarget);
        var pClass,pText = winform.validPattern(win.getClass(hwndTarget)) ,winform.validPattern(winex.getText(hwndTarget,50));

        var hwndPattern = string.format('var hwndParent = winex.find("%s","%s");',pClass,pText);
        if( hwndRoot != hwndTarget ){
            var pClass2,pText2 = winform.validPattern(win.getClass(hwndRoot)) ,winform.validPattern(winex.getText(hwndRoot,50));
            hwndPattern = string.format('var hwndParent = winex.find("%s","%s");\r\nvar hwnd = winex.findEx(hwndParent,,"%s","%s");',pClass2,pText2,pClass,pText);
        }

        import string.template;
        var strCode = string.template();
        strCode.template = /***
//鍒涘缓瑕佹煡鎵剧殑鐩爣鍥惧儚
import soImage;
var imgFind = soImage();
imgFind.setBytes('${jpg}');

//鏌ユ壘绐楀彛
import winex;
${hwnd}

//绐楀彛鎴浘
var imgWindow = soImage();
imgWindow.captureWindow(hwnd);

//鏌ユ壘鐩爣鍥惧儚
var sm,x,y = imgFind.findImage( imgWindow );

//绉诲姩榧犳爣
import mouse;
mouse.moveToWindow(0,0,hwnd);
mouse.moveToWindow(x,y,hwnd,8);
        ***/

        winform.editCode.text =  strCode.format(
            hwnd = hwndPattern;
            jpg = strJpg;
        );
    }
    screenArea.doModal();
}

winform.btnTest.oncommand = function(id,event){
    code = string.trim( winform.editCode.text );
    if(!#code){
        winform.msgboxErr("璇峰厛閫夋嫨鐩爣鍥惧儚");
        return;
    }

    loadcodex(code);
}

winform.validPattern = function(str){
    if(!#str) return "";

    var mbs = string.match(str,"[\s\w]*:+[\s\w]*")
    if(#mbs)
        return mbs;

    str = string.replace(str,"(\p)","\\\1")
    str = string.replace(str,"\x+",function(str){
        if(..string.find(str,"\d") ) return "\x+"
        return str;
    } )

    str = string.replace(str,"\d+","\\d+")
    return str;
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findImage.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findImage.md')

