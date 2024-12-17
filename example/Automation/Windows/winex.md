[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口自动�?- 入门

```aardio aardio
//窗口自动�?- 入门
import winex.key;
import process;

//运行写字�?if( !process.executeWaitInput("wordpad.exe") ){
    error("系统未安装写字板");
}

//查找并等待激活的窗口
var hwnd,hCtrl = winex.waitActive(,,"WordPadClass","RICHEDIT50W");

//win.setFocus,winex.key.combine 等必须要绑定到目标输入线�?winex.attach(hwnd,function(){

    //设置焦点
    win.setFocus(hCtrl)

    //输入一些内�?(你知道aardio发送文本的方式共有多少种吗?)
    winex.key.send(hCtrl,"Test" )
    thread.delay(100)

    //后台发送CTRL+A组合�?    winex.key.combine(hwnd,"CTRL","A")

    //后台发送ALT+F组合�?    winex.key.altClick(hwnd,"F" )
})

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/winex.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/winex.md')

