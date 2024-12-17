[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: richedit 寮瑰嚭鑿滃崟

```aardio aardio
//鍝嶅簲閫氱煡/鍙抽敭鑿滃崟
import win.ui;
/*DSG{{*/
var winform = win.form(text="richedit 寮瑰嚭鑿滃崟";right=432;bottom=279;)
winform.add(
btnSetFont={cls="button";text="鏀瑰彉閫夊尯瀛椾綋";left=240;top=236;right=343;bottom=263;db=1;dr=1;z=2};
richedit={cls="richedit";text="richedit 榛樿娌℃湁鍙抽敭鑿滃崟,
浣跨敤 winform.richedit.popMenu() 鍑芥暟鍒涘缓寮瑰嚭鑿滃崟.
璇风偣鍑昏繖閲岀偣鍑诲彸閿祴璇?";left=28;top=28;right=417;bottom=231;db=1;dl=1;dr=1;dt=1;edge=1;link=1;multiline=1;z=1}
)
/*}}*/

winform.btnSetFont.oncommand = function(id,event){
    /*
    鍏充簬 Text Object Model 璇峰弬鑰僊SDN
    http://msdn.microsoft.com/en-us/library/windows/desktop/bb787607%28v=vs.85%29.aspx
    */
    var textDoc = winform.richedit.getTextObjectModel()
    textDoc.Selection.Font.Name = "闅朵功";
    textDoc.Selection.Font.Bold = textDoc.tomTrue
    textDoc.Selection.Font.Size = 18;
    textDoc.Selection.Font.ForeColor = gdi.RGB(0xff,0xA0,0);

    /*
    //涔熷彲浠ョ敤setSelCharformat鍑芥暟
    winform.richedit.setSelCharformat(
        faceName = "闅朵功";
        yHeight = 200; //瀛椾綋澶у皬鐨勮閲忓崟浣嶆槸锛氱紘(Twips)锛氣�滅(涔熷氨鏄痯t)鈥濈殑1/2
        textColor = gdi.RGB(255,0,0);
    )
    */
}

winform.richedit.onChange = function(){
    winform.text = "鏂囨湰鍙戠敓鏀瑰彉浜?
}

import win.ui.menu;//濡傛灉鏄痚dit鎺т欢蹇呴』瀵煎叆鑿滃崟鏀寔搴?richedit浼氳嚜鍔ㄥ鍏?winform.richedit.enablePopMenu({

    { /*---鍒嗛殧绾?--*/ };

    { "鑷畾涔夎彍鍗曢」";
        function(id){

        } ;
    };

    { "浣跨敤lambda鍑芥暟鎺у埗鏄惁绂佺敤";
        function(id){

        } ; lambda()!winform.richedit.canCopy() ? 1/*_MF_GRAYED*/ : 0
    };
})

////鍙傛暟涔熷彲浠ユ槸杩斿洖鑿滃崟椤规暟缁勭殑鍑芥暟
winform.richedit.enablePopMenu(
    function(){
        var sel = winform.richedit.canCopy();

        return {
            { /*---鍒嗛殧绾?--*/ };

            { "鑷畾涔夎彍鍗曢」";
                function(id){

                } ;
            };

            { "浣跨敤lambda鍑芥暟鎺у埗鏄惁绂佺敤";
                function(id){

                } ; lambda()!sel ? 1/*_MF_GRAYED*/ : 0
            };
        }
    }
)

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/richedit_menu.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/richedit_menu.md')

