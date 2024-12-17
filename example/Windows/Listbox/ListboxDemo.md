[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: button/listbox/edit鎺т欢婕旂ず

```aardio aardio
//鍒楄〃妗嗘帶浠讹紙listbox锛夊熀鏈搷浣?//鎰熻阿 xYe 缂栧啓璇ヨ寖渚?import win.ui;
/*DSG{{*/
var winform = win.form(text="button/listbox/edit鎺т欢婕旂ず";right=397;bottom=171)
winform.add(
btnAdd={cls="button";text="娣诲姞";left=126;top=51;right=172;bottom=75;z=4};
btnClear={cls="button";text="娓呴櫎";left=184;top=52;right=230;bottom=76;z=3};
btnDelete={cls="button";text="鍒犻櫎";left=241;top=52;right=287;bottom=76;z=2};
btnFind={cls="button";text="妯＄硦鏌ユ壘";left=297;top=52;right=360;bottom=76;z=10};
btnFindEx={cls="button";text="绮剧‘鏌ユ壘";left=298;top=83;right=362;bottom=107;z=11};
combobox={cls="combobox";left=128;top=81;right=236;bottom=101;edge=1;items={};mode="dropdown";z=8};
edit={cls="edit";text="璇疯緭鍏?..";left=129;top=20;right=360;bottom=44;acceptfiles=1;edge=1;multiline=1;tabstop=1;z=9};
groupbox={cls="groupbox";text="娣诲姞鍒犻櫎";left=114;top=2;right=379;bottom=165;acceptfiles=1;edge=1;tabstop=1;z=1};
listbox={cls="listbox";left=3;top=3;right=110;bottom=144;acceptfiles=1;bgcolor=16777215;edge=1;items={};tabstop=1;vscroll=1;z=6};
static={cls="static";left=128;top=111;right=360;bottom=158;acceptfiles=1;edge=1;tabstop=1;transparent=1;z=5};
static2={cls="static";text="static2";left=196;top=235;right=197;bottom=236;acceptfiles=1;bgcolor=14215660;tabstop=1;transparent=1;z=7}
)
/*}}*/

winform.btnFindEx.oncommand = function(id,event){
    var ind = winform.listbox.findEx(winform.edit.text);
    winform.listbox.selIndex = ind;
    win.msgbox(ind,"aardio");
}

winform.btnFind.oncommand = function(id,event){ ;
    var ind = winform.listbox.find(winform.edit.text)
    winform.listbox.selIndex = ind
}

winform.combobox.oncommand = function(id,event){
    if(event == 0x1/*_CBN_SELCHANGE*/){
        winform.edit.text = winform.combobox.selText;
    }
}

winform.btnClear.oncommand = function(id,event){
    winform.listbox.clear();
    winform.static.text = "";
    winform.redraw();
}

winform.listbox.oncommand = function(id,event){
    if( event == 0x1/*_LBN_SELCHANGE*/ ){
        winform.static.text =  string.format(
            '鎮ㄩ�変腑浜嗙%d椤筡n鎬昏%d椤筡n椤规枃鏈細%s'
            ,winform.listbox.selIndex
            ,winform.listbox.count
            ,winform.listbox.selText
            );
    }
}

winform.btnDelete.oncommand = function(id,event){
    winform.listbox.delete();
}

winform.btnAdd.oncommand = function(id,event){
    str = winform.edit.text;
    winform.listbox.add(str);
    winform.combobox.add(str);
    winform.combobox.selText =  str;
    winform.listbox.selIndex = winform.listbox.count;
}

winform.show(true);
win.loopMessage( winform );

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/ListboxDemo.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/ListboxDemo.md')

