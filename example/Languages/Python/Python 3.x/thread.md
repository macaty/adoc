[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 后台线程运行 Python

```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio - 后台线程运行 Python";right=799;bottom=447)
winform.add(
button={cls="button";text="调用python线程";left=519;top=367;right=745;bottom=427;z=2};
edit={cls="edit";left=12;top=9;right=784;bottom=348;edge=1;multiline=1;z=1}
)
/*}}*/

/*
如果在界面线程中，Python 需要做耗时操作�?那么可以使用工作线程运行 Python�?
但是要注意在一个进程中只启动一�?Python 线程�?也就是说 Python 本身在唯一的单线程中运行�?
这是因为 Python 存在全局锁，并非真正意义的多线程�?Pyhton 的多线程 GIL 管理比较麻烦，处理不好就会崩溃、死锁�?*/

//Python 后台线程
pyServerThread = function(winform){
    import win.ui;
    import py3;

    //创建命令监听�?    var frmMsg = win.form().messageOnly();

    //响应事件
    frmMsg.pyHash = function(){

        //可以跨线程访问界面控�?        winform.edit.print("子线程正在执�?pyHash 函数",tostring(time()))

        var hashlib = py3.import("hashlib");
        var md5 = hashlib.md5()
        md5.update( raw.buffer("注意这个函数的参数不是字符串而是字节数组（相当于 aardio 中的 buffer�?) );
        sleep(1000)

        //调用界面线的函数
        winform.pyHashEnd( tostring(md5.hexdigest()) );

        return tostring(md5.hexdigest());
    }

    //退出线�?    frmMsg.pyExit = function(){
        win.quitMessage();
    }

    //�?frmMsg 传入界面线程
    winform.pyCommand = frmMsg;

    //在工作线程需要启用消息循环，frmMsg 才能处理消息
    win.loopMessage();
}

//启动 Python 后台线程
thread.create( pyServerThread,winform )

//增加工作线程可以调用的函�?winform.pyHashEnd = function(str){
    winform.edit.print("主线程函数被调用，参数：",str)
}

winform.button.oncommand = function(id,event){

    //禁用按钮，避免重复提�?    winform.button.disabledText = "正在调用python线程";

    //异步调用python线程的函数，等待返回�?    var str = winform.pyCommand.pyHash()
    winform.edit.print("主线程收到返回值：",str)

    //取消按钮禁用状�?    winform.button.disabledText = null;
}

winform.onClose = function(hwnd,message,wParam,lParam){
    //退�?Python 线程
    winform.pyCommand.pyExit()
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/thread.md)

