[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 16杩涘埗缂栬緫鍣?
```aardio aardio
//鍗佸叚杩涘埗缂栬緫鍣?import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
mainForm = win.form(text="hexEditor";right=917;bottom=581;bgcolor=16777215)
mainForm.add(
btnFind={cls="plus";text="鏌ユ壘";left=707;top=523;right=778;bottom=550;align="left";color=3947580;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF002';notify=1;textPadding={left=26};z=3};
btnReplace={cls="plus";text="鏇挎崲";left=707;top=553;right=778;bottom=580;align="left";color=3947580;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF1EA';notify=1;textPadding={left=26};z=5};
btnReplaceAll={cls="plus";text="鍏ㄩ儴鏇挎崲";left=785;top=553;right=885;bottom=580;align="left";color=3947580;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF0CA';notify=1;textPadding={left=26};z=6};
cmbCodePage={cls="combobox";left=784;top=526;right=911;bottom=552;db=1;dr=1;edge=1;items={"UTF-8(65001)";"Unicode(1200)";"Unicode BE(1201)";"ANSI(0)";"GB2312(936)";"BIG5(950)"};mode="dropdownlist";z=7};
editFind={cls="plus";left=16;top=520;right=701;bottom=546;align="right";border={bottom=1;color=-6908266};db=1;dl=1;dr=1;editable="edit";textPadding={top=6;bottom=2};z=2};
editReplace={cls="plus";left=16;top=549;right=701;bottom=575;align="right";border={bottom=1;color=-6908266};db=1;dl=1;dr=1;editable="edit";textPadding={top=6;bottom=2};z=4};
static={cls="static";left=0;top=0;right=919;bottom=514;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

import com.hexEditor;
var hexEditor = com.hexEditor(mainForm.static);
hexEditor.setBuffer('璇锋嫋鍔ㄦ枃浠跺埌褰撳墠绐楀彛');

mainForm.onDropFiles = function(files){
    hexEditor.load(files[1]);
}

import win.clip;
import win.ui.menu;
hexEditor.onContextMenu = function(x,y){
    var menu = win.ui.popmenu(mainForm.static);
    menu.add('澶嶅埗\tCtrl+C',function(){
        hexEditor.copy();
    })

    menu.add('澶嶅埗 16 杩涘埗缂栫爜',function(){
        var hex  = hexEditor.getSelHex()
        if(#hex){
            win.clip.write(hex);
        }
    })

    menu.add('绮樿创\tCtrl+V',function(){
            hexEditor.paste();
    })
    menu.popup(x,y,true);
}

mainForm.btnFind.oncommand = function(id,event){
    var str = string.unhex(mainForm.editFind.text,"\x");
    if(!#str){
        return mainForm.editFind.editBox.showErrorTip("璇疯緭鍏ヨ鏌ユ壘鐨勬暟鎹?);
    }

    hexEditor.findNext(str);
}

mainForm.editFind.setCueBannerText("璇疯緭鍏ユ煡鎵惧瓧绗︿覆锛屾敮鎸佹ā寮忓尮閰嶃�乗x鍓嶇紑 16 杩涘埗瀛楄妭缂栫爜");
mainForm.editReplace.setCueBannerText("璇疯緭鍏ユ煡鎵惧瓧绗︿覆锛屾敮鎸乗x鍓嶇紑鐨?16 杩涘埗瀛楄妭缂栫爜");

mainForm.btnReplace.oncommand = function(id,event){
    var selStart,selEnd = hexEditor.getsel();
    if(!selEnd) return mainForm.btnFind.oncommand();

    var str = string.unhex(mainForm.editReplace.text,"\x");
    hexEditor.replace(str);

    mainForm.btnFind.oncommand();
}

mainForm.btnReplaceAll.oncommand = function(id,event){
    var strFind = string.unhex(mainForm.editFind.text,"\x");
    var strReplace = string.unhex(mainForm.editReplace.text,"\x");

    var buf = hexEditor.getBuffer();
    buf = ..string.replace(buf,strFind,strReplace );
    hexEditor.setBuffer(buf);
}

mainForm.btnFind.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
})

mainForm.btnReplace.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
})

mainForm.btnReplaceAll.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
})

mainForm.cmbCodePage.selIndex = 1;
mainForm.cmbCodePage.onListChange = function(){
    var text = mainForm.cmbCodePage.selText;
    var cp = tonumber(string.match(text,"\((\d+)"));
    if(cp!==null)  {
        cp = tonumber(cp);
        hexEditor.setCodePage(cp);
    }
}

mainForm.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/hexEditor.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/hexEditor.md')

