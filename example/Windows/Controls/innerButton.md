[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 按钮中嵌按钮

```aardio aardio
//按钮嵌按�?import win.ui;
import win.ui.menu;
/*DSG{{*/
var winform = win.form(text="按钮中嵌按钮";right=599;bottom=399;)
winform.add(
btnInner={cls="button";text="4";left=183;top=47;right=209;bottom=77;dr=1;dt=1;font=LOGFONT(charset=2;name='Marlett';weight=500);z=2};
button={cls="button";text="按钮中按�?;left=53;top=43;right=213;bottom=83;dr=1;dt=1;z=1}
)
/*}}*/

/*
winform.btnInner �?winform.button 必须设置相同的固定边距属�?- 以保持在缩放时移动到相同位置
*/

//设置父窗�?winform.btnInner.setParent( winform.button )

//允许父窗口转发子窗口的命令（_WM_COMMAND）与通知（_WM_NOTIFY）消�?winform.button.translateCommand();

/*
响应命令�?_WM_COMMAND 是由控件发送给父窗口，
父窗口解析此消息才能调用控件�?oncommand 函数�?父窗口必须调�?translateCommand() 函数�?*/
winform.btnInner.oncommand = function(id,event){
    //按下鼠标右键,下面获取按钮屏幕坐标
    var rc = winform.btnInner.getRect(true/*使用屏幕坐标*/)

    //创建弹出菜单
    win.ui.popmenu(winform).addTable( {
        {
            "测试";
            function(id){
                winform.msgbox("测试")
            }
        }; {
            "退出程�?;
            function(id){
                winform.close()
            }
        };
    } ).popup(rc.left,rc.bottom,true/*使用屏幕坐标*/)
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/innerButton.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/innerButton.md')

