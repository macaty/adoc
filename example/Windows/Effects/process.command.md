[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 跨进程调用函�?
```aardio aardio
//窗口程序 - 跨进程调用函�?import win.ui;
/*DSG{{*/
mainForm = win.form(text="窗口程序 - 跨进程调用函�?;right=581;bottom=373)
mainForm.add(
button={cls="button";text="发送跨进程命令";left=297;top=309;right=519;bottom=355;z=1};
edit={cls="edit";left=28;top=17;right=555;bottom=298;edge=1;multiline=1;z=2}
)
/*}}*/

import process.command;

//加入进程群组,使用 GUID 区分不同的进程群�?process.command.join("{870819C0-D702-4508-BB0A-5F09E514E23E}")

//注册进程命令对象
var processObserver = process.command();
processObserver.testCmd = function(a,b,c){
    mainForm.edit.appendText("testCmd被调�?参数:",a,b,c,'\r\n');
    return 123;
}

//发送进程命�?mainForm.button.oncommand = function(id,event){
    process.command.testCmd(1,2,",进程命令参数")

}

mainForm.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/process.command.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/process.command.md')

