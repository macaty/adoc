[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用 custom 控件加载自定义控件类

```aardio aardio
//窗口程序 - 定义控件�?
/*
1、拖一�?custom 控件到窗口上�?2、把 custom 控件的类名改为你创建的控件类名，例如 "myCtrl"
3、将窗口编辑器切换到代码模式，并在创建窗口前添加 import win.ui.ctrl.myCtrl 导入该控件�?4、在用户库中 win.ui.ctrl 右键新建窗口类库，例�?win.ui.ctrl.myCtrl
*/

//图文教程: https://mp.weixin.qq.com/s/s95LlTis3lrVeD8EYNZD0w
//这里直接定义控件类，实际使用建议写到用户库里
import inet.http;
import win.ui;

class win.ui.ctrl.myCtrl{
    ctor( parent,tParam ){
        /*
        parent 参数为父窗口
        tParam 参数为创建控件的所有参�?        */
        this = ..win._form(border="none";exmode="none";mode="child";parent=parent;right=750;bottom=387;tParam=tParam)
        this.add(
            plus={cls="plus";left=-5;top=2;right=751;bottom=393;db=1;dl=1;dr=1;dt=1;repeat="scale";z=1}
        )

        /*
        控件类只要在 this.hwnd 里存在有效的窗口句柄就表示创建子窗口成功�?        win.form 创建成功会将句柄保存�?this.hwnd 中�?
        如果控件类构造函数返回的对象不存�?this.hwnd �?        那么 aardio 会使�?tParam.cls 的类名创建控件，所以也可以在这里指定有效的控件类名�?        例如 win.ui.ctrl.listview 的构造函数里就是这样写：
        tParam.cls = "SysListView32";
        注意这里无论怎样修改 tParam.cls，控件创建成功后都会改回上面参数传入的原�?tParam.cls 的值�?        */
    };
}
/*DSG{{*/
var winform = win.form(text="使用 custom 控件加载自定义控件类";right=836;bottom=513)
winform.add(
custom={cls="myCtrl";text="自定义控�?;left=3;top=-1;right=467;bottom=316;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

winform.show();

//这时�?winform.custom 就是 win.ui.ctrl.myCtrl 的实例对�?
winform.custom.plus.background = "http://download.aardio.com/v10.files/demo/images/custom.gif";

/*
不需要用 import 语句导入标准�?win.ui.ctrl 名字空间下的自带控件�?aardio 会按需导入这些标准库控件，但是如果是自己添加的自定义控件就要提前导入�?如果�?win.ui.ctrl.myCtrl 写到外部类库里，那就一定要�?import win.ui.ctrl.myCtrl 提前导入该控件类�?*/

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Custom/cls.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Custom/cls.md')

