[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 文本框提�?
```aardio aardio
//文本框提�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
btnError={cls="button";text="错误";left=280;top=306;right=390;bottom=353;z=2};
btnInfo={cls="button";text="提示";left=539;top=306;right=649;bottom=353;z=4};
btnWarning={cls="button";text="警告";left=410;top=306;right=520;bottom=353;z=3};
edit={cls="edit";text="Edit";left=129;top=179;right=394;bottom=218;edge=1;multiline=1;z=1}
)
/*}}*/

winform.btnError.oncommand = function(id,event){
    winform.edit.showErrorTip("这是标题","这是要显示的错误信息")
}

winform.btnWarning.oncommand = function(id,event){
    winform.edit.showWarningTip("这是标题","这是要显示的错误信息")
}

winform.btnInfo.oncommand = function(id,event){
    winform.edit.showInfoTip("这是标题","这是要显示的错误信息",true)
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/edit.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Tooltip/edit.md')

