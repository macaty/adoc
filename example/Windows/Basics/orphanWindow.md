[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - orphanWindow

```aardio aardio
//窗口程序 - orphanWindow
import win.ui;
/*DSG{{*/
var winform = win.form(text="智能提示";right=600;bottom=400)
winform.add(
edit={cls="edit";left=190;top=301;right=525;bottom=327;db=1;dl=1;dr=1;edge=1;multiline=1;z=1};
richedit={cls="richedit";text="RichEdit";left=473;top=20;right=968;bottom=145;edge=1;multiline=1;z=2}
)
/*}}*/

winform.richedit.orphanWindow();
/*
orphanWindow �?aardio 实现的一种全新的窗口模式�?orphanWindow 即悬浮窗口，指的是普通的控件窗口孤立出来成为独立窗口�?但是仍然可以显示在原来的位置，如影随形的跟随父窗口移动、显示、隐藏�?在外观上用户仍然以为这是父窗口上的子窗口，感觉不到这是一个独立的窗口�?orphanWindow 与子窗口不同的是可以显示在父窗口的显式区域之外�?
我们还可以这样写�?winform.custom.orphanWindow(,hwndBuddy)
上面�?winform.custom �?custom 控件，hwndBuddy 可以指定一个外部进程创建的窗口句柄�?
winform.custom.orphanWindow(,hwndBuddy)
将外部进程窗口转化为 aardio 中独有的 orphanWindow，成为吸附在 aardio 窗口上的伪子窗口�?
这可以用来解决一些比较复杂的问题，实现一些难以实现的效果�?例如 Electron 创建的窗口嵌入为子窗口时会出现一些诡异的问题（不是每个版本都有，并且只在部分系统出现）�?但如果使�?orphanWindow 的功能将 Electron 窗口托管给悬浮窗口，就可以解决这些问题�?具体请参考标准库�?electron.app 的源代码�?*/

//orphanWindow 可以轻松的实现原来很复杂的功能，例如下面演示的智能提示列�?import web.rest.jsonLiteClient;
var http = web.rest.jsonLiteClient();
var suggestion = http.api("http://suggestion.baidu.com/su?cb=&wd={0}");
//{0}会替换为请求关键字并以UTF8编码,这个API返回数据是GBK编码

/*
listbox �?orphanWindow 模式显示时不能再响应事件,
这时候我们把 listbox 放在一�?custom 控件里，再把custom控件显示�?orphanWindow�?因为 custom 是一�?win.form 对象,所�?listbox 可以响应事件了�?细节请查�?win.ui.listPopup 源码,
*/
import win.ui.listPopup;
var listPopup = win.ui.listPopup(winform.edit);
listPopup.onGetItems = function(){
    var items =  suggestion[ winform.edit.text ].get().s;
    if(!#items) return;

    var selIndex = 1;
    reduce(items,function(prev,next,index){
        if( #next < #prev ) { selIndex = index; return next };
        return prev
    })

    return items,selIndex;
}

winform.show(true);
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/orphanWindow.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/orphanWindow.md')

