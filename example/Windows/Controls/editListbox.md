[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 编辑listbox

```aardio aardio
//编辑listbox
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=349;bottom=249 )
winform.add(
listbox={ bgcolor=16777215;bottom=192;right=284;left=75;top=36;
items={ "ddddddddddd";"cccc";"双击编辑" };z=1;text="listbox";edge=1;cls="listbox" }
)
/*}}*/

var lstEdit = winform.listbox.addCtrl(
    edit = {
        cls="edit";
        left=0;top=0;right=50;bottom=50;
        autoResize=false ;
        hide=1;
        edge=1;
        wndproc = function(hwnd,message,wparam,lparam){
            if( message == 0x8/*_WM_KILLFOCUS*/
                || (message==0x101/*_WM_KEYUP*/ && wparam == 0xD/*_VK_ENTER*/) ) {
                if( owner.selIndex){
                    winform.listbox.add(owner.text,owner.selIndex)
                    winform.listbox.delete(owner.selIndex+1)
                    owner.hide = true;
                    winform.listbox.redraw()
                }
            }
        };
    }
).edit

winform.listbox.oncommand = function(id,event){
    if( event ==  0x2/*_LBN_DBLCLK*/ ){

        var rc = owner.getItemRect( owner.selIndex )
        rc.bottom += 5;
        lstEdit.setRect(rc)

        lstEdit.hide = false;
        lstEdit.text = winform.listbox.selText;
        lstEdit.selIndex = owner.selIndex ;
    }
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/editListbox.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/editListbox.md')
