[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎸夐挳涓祵鎸夐挳

```aardio aardio
//鎸夐挳宓屾寜閽?import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="鎸夐挳涓祵鎸夐挳";right=599;bottom=399;)
winform.add(
btnInner={cls="button";text="4";left=183;top=47;right=209;bottom=77;dr=1;dt=1;font=LOGFONT(charset=2;name='Marlett';weight=500);z=2};
button={cls="button";text="鎸夐挳涓寜閽?;left=53;top=43;right=213;bottom=83;dr=1;dt=1;z=1}
)
/*}}*/

/*
winform.btnInner 涓?winform.button 蹇呴』璁剧疆鐩稿悓鐨勫浐瀹氳竟璺濆睘鎬?- 浠ヤ繚鎸佸湪缂╂斁鏃剁Щ鍔ㄥ埌鐩稿悓浣嶇疆
*/

//璁剧疆鐖剁獥鍙?winform.btnInner.setParent( winform.button )

//鍏佽鐖剁獥鍙ｈ浆鍙戝瓙绐楀彛鐨勫懡浠わ紙_WM_COMMAND锛変笌閫氱煡锛坃WM_NOTIFY锛夋秷鎭?winform.button.translateCommand();

/*
鍝嶅簲鍛戒护銆?_WM_COMMAND 鏄敱鎺т欢鍙戦�佺粰鐖剁獥鍙ｏ紝
鐖剁獥鍙ｈВ鏋愭娑堟伅鎵嶈兘璋冪敤鎺т欢鐨?oncommand 鍑芥暟銆?鐖剁獥鍙ｅ繀椤昏皟鐢?translateCommand() 鍑芥暟锛?*/
winform.btnInner.oncommand = function(id,event){
    //鎸変笅榧犳爣鍙抽敭,涓嬮潰鑾峰彇鎸夐挳灞忓箷鍧愭爣
    var rc = winform.btnInner.getRect(true/*浣跨敤灞忓箷鍧愭爣*/)

    //鍒涘缓寮瑰嚭鑿滃崟
    win.ui.popmenu(winform).addTable( {
        {
            "娴嬭瘯";
            function(id){
                winform.msgbox("娴嬭瘯")
            }
        }; {
            "閫�鍑虹▼搴?;
            function(id){
                winform.close()
            }
        };
    } ).popup(rc.left,rc.bottom,true/*浣跨敤灞忓箷鍧愭爣*/)
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/innerButton.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/innerButton.md')

