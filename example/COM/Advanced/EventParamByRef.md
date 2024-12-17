[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - 事件输出参数

```aardio aardio
//COM 接口 - 事件输出参数
import win.ui;
/*DSG{{*/
var winform = win.form(text="用连接点注册事件";right=964;bottom=605)
winform.add(
edit={cls="edit";left=22;top=524;right=937;bottom=584;db=1;dl=1;dr=1;edge=1;multiline=1;vscroll=1;z=2};
static={cls="static";left=22;top=17;right=938;bottom=510;db=1;dl=1;dr=1;dt=1;edge=1;z=1}
)
/*}}*/

//嵌入 COM 控件
var browser = winform.static.createEmbedEx("Shell.Explorer.2");

//定义事件�?browser.BeforeNavigate2 = function( pDisp, url, flags, targetFrame, postData, headers, cancel ) {
    winform.edit.print("BeforeNavigate2",url);

    /*
    aardio 基于纯函数原则，不会直接通过修改参数输出值，
    如果是引用或输出参数，可在返回值里返回新的参数值�?
    首先是返回函数本身的返回值（没有就不用返回）�?    然后依传入的前后顺序返回所有输出参数的值，
    可以省略返回值，但不能改变返回值的位置�?
    例如这个事件，cancel 参数返回 true 就可以阻止打开 url 参数指定的网址�?    �?cancel 必须是第 6 个返回值�?    */
    return url, flags, targetFrame, postData, headers, cancel;

    //阻止网页打开
    //return url, flags, targetFrame, postData, headers, true;
};

//调用 COM 对象打开网页
browser.Navigate("about:hello");

winform.show(3/*_SW_MAXIMIZE*/);
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Advanced/EventParamByRef.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Advanced/EventParamByRef.md')

