[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 文本框点击全�?
```aardio aardio
//点击全�?import win.ui;
/*DSG{{*/
var winform = win.form(text="文本框点击全�?;right=759;bottom=469)
winform.add(
edit={cls="edit";text="Edit";left=47;top=35;right=371;bottom=65;dl=1;dt=1;edge=1;hidesel=1;multiline=1;tabstop=1;z=1};
edit2={cls="edit";text="Edit";left=45;top=101;right=369;bottom=131;dl=1;dt=1;edge=1;hidesel=1;multiline=1;tabstop=1;z=2};
richedit={cls="richedit";text="RichEdit";left=45;top=160;right=243;bottom=220;dl=1;dt=1;edge=1;multiline=1;tabstop=1;z=3}
)
/*}}*/

winform.edit.onFocusGot = function(){
    winform.setTimeout( lambda() winform.edit.selectAll() );
}

winform.edit2.onFocusGot = function(id){
    winform.setTimeout( lambda() winform.edit2.selectAll() );
}

/*
如果在点击获得焦点时直接全选，
在全选以后窗口会继续处理鼠标消息，导致选区被取消�?所以我们需要先从事件中返回让，并使�?winform.setTimeout 延后执行全选操作�?*/
winform.richedit.onFocusGot = function(id){
    winform.setTimeout( lambda() winform.richedit.selectAll() );
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/selectAllOnFocus.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/selectAllOnFocus.md')

