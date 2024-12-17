[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 退出远程桌面，保持会话

```aardio aardio
//保持远程桌面会话
import win.ui;
/*DSG{{*/
var winform = win.form(text="退出远程桌面，保持会话";right=759;bottom=469)
winform.add(
button={cls="button";text="退出远程桌�?;left=395;top=399;right=738;bottom=458;color=14120960;font=LOGFONT(h=-14);note="退出后保持会话，自动化程序可继续运�?;z=1};
edit={cls="edit";left=18;top=20;right=742;bottom=388;edge=1;multiline=1;z=2}
)
/*}}*/

import win.ts.changeNotification;
var changeNotification = win.ts.changeNotification(winform);
changeNotification.onSessionChange = function(sessionId,statusText,statusCode){
    winform.edit.print("会话ID:" + sessionId,statusText,statusCode);
}

import win.ts;
winform.button.oncommand = function(id,event){
    //退出远程桌面，保持会话，窗口自动化程序可继续运�?    win.ts.session().connect();
}

/*
创建远程桌面客户端请参考：
范例程序 > COM 组件 > 免注册控�?> 远程桌面
*/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/win.ts.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/win.ts.md')

