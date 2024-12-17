[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 使用自定义控件创建子窗体容器

```aardio aardio
//窗口程序 - 使用自定义控件创建子窗体容器
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
button1={cls="button";text="切换窗口 frmChild1";left=366;top=418;right=525;bottom=459;db=1;dr=1;z=2};
button2={cls="button";text="切换窗口 frmChild2";left=534;top=418;right=693;bottom=459;db=1;dr=1;z=3};
custom={cls="custom";text="自定义控�?;left=21;top=14;right=741;bottom=380;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

/*
我们可以使用 winform.custom.loadForm( path ) 加载窗口�?aardio 会自动将窗口加载�?winform.custom 的子窗口�?
每次调用 winform.custom.loadForm( path )都会加载窗体代码并返回新的子窗体对象�?winform.custom 会成为容器管理所有加载的子窗口数组�?
规则如下�?1、当显示一个子窗口，其他子窗口就会自动隐藏�?2、调�?winform.custom.loadForm( path ) 并不会释放之前加载的其他子窗体，而仅仅是隐藏他们�?2、当关闭一个子窗口，他就会自动�?custom 控件容器的子窗口数组中移除�?*/

var frmChild1 = winform.custom.loadForm("/.res/frmChild1.aardio")
winform.button1.oncommand = function(id,event){
    frmChild1.show();
}

var frmChild2 = winform.custom.loadForm("/.res/frmChild2.aardio")
winform.button2.oncommand = function(id,event){
    frmChild2.show();
    /*
    如果在函数内部调�?winform.custom.loadForm("/.res/frmChild2.aardio")
    又不关闭以前加载的子窗口，就会导致每点击一次都加载一个新的窗口，
    且并没有释放之前的窗口（ 他们之是被隐藏了 ）�?
    所以我们并不需要在这里重复加载同一窗体文件，只要简单的显示他就可以了�?    */
}

/*
标准�?win.ui.tabs 实现的「高级选项卡就会自动查找附近合适的 custom 控件作为子窗口容器�?*/

winform.show();
win.loopMessage();
return winform;

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Custom/container.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Custom/container.md')

