[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: richedit 富文本框控件如何插入超链�?
```aardio aardio
//插入超链�?import win.ui;
/*DSG{{*/
var winform = win.form(text="richedit 富文本框控件如何插入超链�?;right=759;bottom=469)
winform.add(
button={cls="button";text="Button";left=423;top=397;right=670;bottom=436;z=2};
richedit={cls="richedit";text="添加超链�?;left=16;top=11;right=749;bottom=379;edge=1;hidesel=false;link=1;multiline=1;z=1}
)
/*}}*/

//启用自动识别超链接功能，或者在 richedit 控件的设计器属性中指定「识别链接」为 true�?winform.richedit.link = true;

//自动识别文本中的超链接，添加超链接样式，并响应点击事�?winform.richedit.text = "自动识别超链接： http://www.aardio.com  "

//响应按钮事件
winform.button.oncommand = function(id,event){

    //设置选区文本的超链接请调�?winform.richedit.setLink 函数
    //手动添加超链接，会自动禁用自动识别超链接功能，不会影响之前识别出来的超链接效�?    winform.richedit.appendLink(
        "点这里打开超链�? ,"http://www.aardio.com"
    );

}

//自定义超链接消息处理程序，这是可选的。控件默认会自动添加下面�?onHyperlink 处理程序
winform.richedit.onHyperlink =function(message,href){

    if( message = 0x202/*_WM_LBUTTONUP*/ ) {
        raw.execute(href);
    }
}

//显示窗口
winform.show();

//启动界面线程消息循环
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/onHyperlink.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/onHyperlink.md')

