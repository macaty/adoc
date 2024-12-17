[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 适用�?edit / richedit

```aardio aardio
//文本�?- tab �?import win.ui;
/*DSG{{*/
var winform = win.form(text="适用�?edit / richedit";right=727;bottom=357;bgcolor=16777215)
winform.add(
edit={cls="edit";text='多行，禁用「tab 控制键」，按回车换行。\r\n定义 winform.edit.isDialogMessage 在控件范围屏蔽对话框快捷键，以支持按 tab 输入制表符，代码如下：\r\n \r\nwinform.edit.isDialogMessage = function(hParent,msg){}';left=20;top=221;right=710;bottom=337;edge=1;multiline=1;z=4};
edit1={cls="edit";text="单行，启用「tab 控制键」，�?tab 或回�?切换焦点";left=20;top=16;right=710;bottom=41;edge=1;multiline=1;tabstop=1;z=1};
edit2={cls="edit";text="单行，启用「tab 控制键」，�?tab 或回�?切换焦点";left=20;top=53;right=710;bottom=78;edge=1;multiline=1;tabstop=1;z=2};
edit3={cls="edit";text="多行，启用「tab 控制键」，�?tab  切换焦点，按回车换行";left=20;top=87;right=710;bottom=203;edge=1;multiline=1;tabstop=1;z=3}
)
/*}}*/

//多行文本框如下支持按 tab 输入制表符，控件设计属性「tab控制键」必须为 false（默认值）�?winform.edit.isDialogMessage = function(hParent,msg){}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/tab.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/tab.md')

