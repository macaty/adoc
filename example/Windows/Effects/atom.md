[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 原子窗体一�?
```aardio aardio
//原子窗体一�?
/*
有时候进程需要禁止重复运�?但主窗体可能并不是最先启动的(例如登录界面、欢迎界面等�?
这时候就不方便在第一个窗体使用原子窗体禁止重复启�?可以改用 process.mutex 创建互斥体来禁止进程重复启动�?仍然可以通过原子窗体尝试查找主窗�?实现用户双击EXE激活已经启动的主窗体的效果�?*/

//创建互斥�?import process.mutex;
var mutex = process.mutex("互斥�?唯一标识")
if( mutex.conflict ){
    import win.ui.atom;
    var atom,hwndConflict = win.ui.atom.find("原子窗体.唯一标识")
    if( hwndConflict ) win.setForeground(hwndConflict);
    return;
}

import win.ui;
/*DSG{{*/
var winform = win.form( text="aardio form";right=349;bottom=249 )
winform.add(  )
/*}}*/

import win.ui.atom
winform.atom("原子窗体.唯一标识");

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/atom.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/atom.md')

