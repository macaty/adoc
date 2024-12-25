[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 多线�?—�?入门

```aardio aardio
import win.ui;
/*DSG{{*/
var winform = win.form(text="多线�?—�?入门";right=536;bottom=325)
winform.add(
button={cls="button";text="启动线程";left=27;top=243;right=279;bottom=305;db=1;dl=1;dr=1;font=LOGFONT(h=-16);z=1};
edit={cls="edit";left=27;top=20;right=503;bottom=223;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=2}
)
/*}}*/

//多线程入门指�? https://www.aardio.com/zh-cn/doc/guide/language/thread.html
winform.button.oncommand = function(id,event){

    //禁用按钮并显示动�?    winform.button.disabledText = {"�?;"�?;"�?;"�?;"�?;"�?}

    //创建工作线程
    thread.invoke(

        //线程启动函数
        function(winform){

            for(i=1;3;1){
                sleep(1000); //在界面线程执�?sleep 会卡�?
                //调用界面控件的成员函�?- 会转发到界面线程执行
                winform.edit.print("工作线程正在执行，时间：" + tostring( time() ) );
            }

            winform.button.disabledText = null;

        },winform //窗口对象可作为参数传入工作线�?    )
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Thread/QuickStart.md)

