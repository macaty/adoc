[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 预处理通知消息

```aardio aardio
//窗口程序 - 预处理通知消息
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
edit={cls="edit";left=301;top=8;right=734;bottom=443;edge=1;multiline=1;z=2};
treeview={cls="treeview";left=18;top=8;right=276;bottom=443;asel=false;bgcolor=16777215;edge=1;z=1}
)
/*}}*/

/********
预处理通知消息属于标准库保留自用的接口�?原则�?aardio 不建议在普通代码中使用此功能�?如果必须要使用，也应当用于编写底层库模块，不可用于一般性代码�?
预处理通知消息提供了一个机会可以提前拦截控件的通知消息�?并在 onnotify 事件之前触发。在预处理消息的回调函数中，
返回任何�?null 值会阻止继续调用 onnotify 回调�?
如果编写控件库，在控件的属性元表中
必须使用带下划线�?_prenotify 定义预处理通知消息�?例如 win.ui.tooltip 源码中是这样写的�?
win.ui.tooltip._metaProperty = ..win.ui.ctrl.metaProperty(
    _prenotify = {
        [0xFFFFFDF7/*_TTN_SHOW*/] = function(id,code,ptr){
            if(owner.onPopupShow)owner.onPopupShow();
        };
    }
)

但是在控件创建以后，
_prenotify 会被属性元表接管，不再允许直接修改�?这时候应当使用去掉下划线�?prenotify 定义预处理通知消息�?
例如 win.ui.explorer 的源码里是这样写的：
this.treeview.prenotify = {
    [0xFFFFFFFE/*_NM_CLICK*/] = function(id,code,ptr){
        var hItem,flags = this.treeview.hitTest()
        if( hItem  && this.onClick && ( flags & 6/*_TVHT_ONITEMLABEL | _TVHT_ONITEMICON*/) ){
            this.onClick( this.getFilePath(hItem),hItem );
        }
    };
};

控件�?prenotify 可以被重复赋值，
每次赋值都会与之前定义�?prenotify 合并�?同一个通知代码只能定义一个回调，新的总是覆盖旧的�?
_prenotify �?prenotify 应当总是定义为表对象�?如果�?_prenotify 定义为函数，将不能再通过 prenotify 进行修改预处理通知消息�?如果你是控件库的第一作者，并且清楚所导致的后果，那么你可以这样做�?
如果不是清楚的了解自己在做什么，
任何时候都不应当覆盖标准库定义的预处理通知消息�?********/

winform.treeview.onnotify = function(id,code,ptr){
    if(code==0xFFFFFFFE/*_NM_CLICK*/){
        var hItem,flags = winform.treeview.hitTest()
        if( hItem ){
            winform.edit.print("winform.treeview.onnotify",winform.treeview.getItemText(hItem));
        }
    }
}

//在代码提示、库函数文档中都会隐藏这个属性，因为我们并不建议普通用户使用�?winform.treeview.prenotify = {
    [0xFFFFFFFE/*_NM_CLICK*/] = function(id,code,ptr){
        if(0xFFFFFFFE/*_NM_CLICK*/){
            var hItem,flags = winform.treeview.hitTest()
            if( hItem ){
                winform.edit.print("winform.treeview.prenotify",winform.treeview.getItemText(hItem));
            }
        }
    }
}

winform.treeview.insertItem( {
    text = "下面用一个数组指定子节点"; {
        {  text = "子节�?"  };
        {  text = "子节�?" };
        {  text = "下面用一个数组指定子节点"; {
            "a";"b";"c";{ text = "d" }
           }
        };
    }
} )

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/prenotify.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/prenotify.md')

