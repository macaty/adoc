[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍒楄〃妗嗘帶浠讹紙listbox锛?- 鍙抽敭鑿滃崟

```aardio aardio
//鍒楄〃妗嗘帶浠讹紙listbox锛?- 鍙抽敭鑿滃崟
import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="aardio form";right=408;bottom=314;)
winform.add(
listbox={cls="listbox";left=15;top=16;right=392;bottom=290;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;edge=1;items={"娴嬭瘯椤圭洰";"璇峰湪杩欓噷鐐瑰嚮榧犳爣鍙抽敭";"璇峰湪杩欓噷鐐瑰嚮榧犳爣鍙抽敭,娴嬭瘯椤圭洰"};z=1}
)
/*}}*/

//鍒涘缓寮瑰嚭鑿滃崟
winform.popmenu = win.ui.popmenu(winform);
winform.popmenu.add('鍒犻櫎',function(id){
        winform.listbox.delete()
} )

winform.listbox.wndproc = function(hwnd,message,wParam,lParam){
    select( message ) {
        case 0x205/*_WM_RBUTTONUP*/{
            var x,y = win.getMessagePos();
            var item = winform.listbox.hitTest(x,y,true);
            if( item ){
                winform.listbox.selIndex = item;
                winform.popmenu.popup(x,y,true)
            }
        }
    }
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/menu.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/menu.md')

