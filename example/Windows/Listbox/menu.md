[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 列表框控件（listbox�?- 右键菜单

```aardio aardio
//列表框控件（listbox�?- 右键菜单
import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="aardio form";right=408;bottom=314;)
winform.add(
listbox={cls="listbox";left=15;top=16;right=392;bottom=290;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;edge=1;items={"测试项目";"请在这里点击鼠标右键";"请在这里点击鼠标右键,测试项目"};z=1}
)
/*}}*/

//创建弹出菜单
winform.popmenu = win.ui.popmenu(winform);
winform.popmenu.add('删除',function(id){
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

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/menu.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Listbox/menu.md')

