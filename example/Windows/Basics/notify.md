[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: WM\_NOTIFY 消息�?onnotify 事件

```aardio aardio
//窗口程序 - 响应控件通知
import win.ui;
/*DSG{{*/
var winform = win.form(text="WM_NOTIFY 消息�?onnotify 事件";right=634;bottom=382;)
winform.add(
listview={cls="listview";left=17;top=36;right=619;bottom=360;acceptfiles=1;asel=false;bgcolor=16777215;dl=1;dr=1;edge=1;font=LOGFONT(name='SimSun');fullRow=1;gridLines=1;msel=false;z=1};
static={cls="static";text="请使用鼠标左键点击不同的列表�?;left=17;top=10;right=290;bottom=28;transparent=1;z=2}
)
/*}}*/

/**************
一个窗口内的控件发生了一些事情，需要通知父窗口，就会发�?_WM_COMMAND 或�?_WM_NOTIFY 消息给父窗口.

最初Windows 3.x 就有的标准控�?Standard Controls)，如Edit，Combobox，Listbox，Button等，发送的控件通知消息的格式是 WM_COMMAND�?而后期的 Win32 通用控件(Common Controls)，如List View，Image List，IP Address，Tree View，Toolbar 等，发送的都是 WM_NOTIFY 控件通知消息�?另外，当用户选择菜单的一个命令项，也会发�?_WM_COMMAND 消息�?
早期开发桌面软件使用的�?C++ 这样的静态语言，通常主要代码都是写在父窗口中，所以这种通知父窗口的消息一定意义上来说提供了方便�?但是�?aardio 这样的动态语言中这种方式意义不大，在父窗口上处理所有子控件的消息其实是相对麻烦且不必要的，所�?aardio 将这些消息重新发回给控件对象自己处理�?
�?aardio 中通过控件�?oncommand 函数处理自身发出�?_WM_COMMAND 消息�?通过控件�?onnotify 函数处理自身发出�?_WM_NOTIFY 消息�?
�?aardio 开发环境的窗体设计器中，右键点击控件，
在弹出菜单中点击「响应命令」就可以为该控件添加 oncommand 函数�?在弹出菜单中点击「响应通知」就可以为该控件添加 onnotify 函数�?
窗口控件库参考文档：
https://docs.microsoft.com/zh-cn/windows/win32/controls/individual-control-info
**************/
winform.listview.onnotify = function(id,code,ptr){

    //code 参数也就�?WM_NOTIFY 通知消息�?wParam 参数.
    //参考文档： https://docs.microsoft.com/zh-cn/windows/win32/controls/list-view-control-reference#notifications
    select(code) {

        //不同的控件，不同的通知消息具体怎么处理可参考微软文�?        case  0xFFFFFF9B/*_LVN_ITEMCHANGED*/ {
            /*
            ptr 参数也就�?WM_NOTIFY 通知消息�?lParam 参数，是一个指�?::NMHDR 结构体的指针�?            不同的通知消息，这个指针实际指向的结构体可能是�?::NMHDR 基础上扩展了其他字段的不同结构体.
            例如 _LVN_ITEMCHANGED 这里�?ptr 指向 NMLISTVIEW 结构体�?
            请右键点�? winform.listview.getNotifyMessage
            然后在弹出菜单点「跳到定义」查看该函数源码�?            */
            var nm = winform.listview.getNotifyMessage(code,ptr)
            if(winform.listview.selIndex){
                winform.static.text = "选中�? +  winform.listview.getItemText(nm.iItem,nm.iSubItem)
            }
        }
    }

}

winform.listview.setColumns("列标�?","列标�?");
winform.listview.addItem({"第一行内�?;"yes"} );
winform.listview.addItem("第二行内�?);
winform.listview.addItem("第三行内�?);

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/notify.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/notify.md')

