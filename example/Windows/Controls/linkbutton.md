[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 按钮附注 / 命令链接按钮

```aardio aardio
//按钮附注
import win.ui;
/*DSG{{*/
var winform = win.form(text="按钮附注  / 命令链接按钮";right=599;bottom=399)
winform.add(
button={cls="button";text="Command Link";left=131;top=162;right=360;bottom=228;note="按钮显示为「命令链接」样�?;z=1}
)
/*}}*/

winform.button.oncommand = function(id,event){
    /*
    �?button 设计属性中指定按钮附注 - Vista,Win7 以及之后的系统自动切换为「命令链接」样�?    */
    winform.button.note = "已修改按钮附�?;
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/linkbutton.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/linkbutton.md')

