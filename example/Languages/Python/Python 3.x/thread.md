[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中通过后台线程运行 Python 解释�?
```aardio aardio
//�?aardio 中通过后台线程运行 Python 解释�?import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio - 后台线程运行 Python";right=1163;bottom=753)
winform.add(
button={cls="button";text="调用python线程";left=876;top=663;right=1102;bottom=723;z=2};
edit={cls="edit";left=11;top=16;right=1140;bottom=625;edge=1;multiline=1;z=1}
)
/*}}*/

/*
Python 存在全局锁，并非真正意义的多线程�?Pyhton 的多线程 GIL 管理也不方便，处理不好就会崩溃、死锁�?这是 Python 的限制与 aardio 无关�?
更好的方式是在单线程中运�?Python�?如果在界面线程中，Python 需要做耗时操作�?那么可以使用工作线程运行 Python，下面是一个演示：
*/

//python服务端线�?pyServerThread = function(winform){
    import thread.command;
    import py3;

    //创建命令监听�?    var cmd = thread.command();

    //响应事件
    cmd.pyHash = function(){

        //可以直接访问界面控件
        winform.edit.print("子线程正在执�?pyHash 函数",tostring(time()))

        var hashlib = py3.import("hashlib");
        var md5 = hashlib.md5()
        md5.update( raw.buffer("注意这个函数的参数不是字符串而是字节数组（相当于 aardio 中的 buffer�?) );
        sleep(1000)

        //调用界面线的函数
        winform.pyHashEnd( tostring(md5.hexdigest()) );

        return tostring(md5.hexdigest());
    }

    //退出线�?    cmd.pyExit = function(){
        win.quitMessage();
    }

    //在工作线程需要启用消息循环，才能响应事件
    win.loopMessage();
}

//启动python服务端线�?thread.create( pyServerThread,winform )

//增加工作线程可以调用的函�?winform.pyHashEnd = function(str){
    winform.edit.print("主线程收到：",str)
}

import thread.command;
winform.button.oncommand = function(id,event){

    //禁用按钮，避免重复提�?    winform.button.disabledText = "正在调用python线程";

    //异步调用python线程的函数，不等待返�?    thread.command.post("pyHash")

    //异步调用python线程的函数，等待返回�?    var str = thread.command.sendInvoke("pyHash")
    winform.edit.print("主线程收到：",str)

    //取消按钮禁用状�?    winform.button.disabledText = null;
}

winform.onClose = function(hwnd,message,wParam,lParam){
    //退出Python线程
    thread.command.pyExit()
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/thread.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/thread.md')

