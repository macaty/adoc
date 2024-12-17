[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 超链接控件测�?
```aardio aardio
//超链接控�?//如何在界面上快速添加超链接，如何利用自定义控件实现超链�?import win.ui;
/*DSG{{*/
var winform = win.form(text="超链接控件测�?;right=713;bottom=504)
winform.add(
lnkWebsite={cls="syslink";text="使用 syslink 控件教程";left=84;top=30;right=279;bottom=97;transparent=1;z=1};
plus={cls="plus";left=37;top=99;right=633;bottom=426;repeat="center";z=2}
)
/*}}*/

/*
添加超链接控件的步骤�?
1. 自『界面控件』工具箱拖一�?custom 控件到界面上�?2. �?custom　控件的类名改�?"syslink"�?3. 使用控件的文本（text）属性指定超链接显示的文本�?4. 在代码中使用 link 属性创建第一个超超链接�?*/

winform.lnkWebsite.link =  "http://www.aardio.com";//快速设置或修改超链�?
/*
通过控件�?text 属性可使用 HTML 语法创建一个或多个超链接�?除普通文本与超链接以外，不支持其�?HTML 语真法，例如文本应当直接换行而不是用 <br> 换行�?*/
winform.lnkWebsite.text = `<a
href="http://bbs.aardio.com/forum.php?mod=viewthread&tid=13220&extra=&from=portal"
id="也可以指�?ID">使用 syslink 控件教程</a>

<a href="https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/ctrl/custom.html#cls">使用自定义控件教�?/a>
`

/*
可选自定义打开超链接的函数�?不指�?onHyperlinkClick 则默认调�?raw.execute 打开超链�?
*/
winform.lnkWebsite.onHyperlinkClick = function(nmSysLink,url,id,index){
    //打开超链接，如果控件有多个链接可以使�?index 区分（第一个超链接  index �?�?    raw.execute(url)
}

import inet.http;//支持远程图像
winform.plus.background = "https://download.aardio.com/v10.files/demo/syslink.gif"

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/syslink.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/syslink.md')

