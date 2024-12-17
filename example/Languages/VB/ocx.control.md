[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 免注册嵌�?VB 控件

```aardio aardio
//免注册嵌入VB控件
//讲解此范例的教程: https://mp.weixin.qq.com/s/Gp8aM_YruBE5KZF-jC-p3A
//VB 快速入�? https://learnxinyminutes.com/docs/zh-cn/visualbasic-cn
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="免注册嵌�?VB 控件";right=700;bottom=304)
winform.add(
btnOpenVbp={cls="plus";text="查看VB控件源码";left=491;top=256;right=651;bottom=286;align="left";bgcolor=-5197169;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=20}};iconText='\uF121';notify=1;textPadding={left=39};z=3};
edit={cls="edit";left=356;top=20;right=665;bottom=243;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
static={cls="static";text="Static";left=21;top=20;right=330;bottom=243;dl=1;dt=1;transparent=1;z=1};
static2={cls="static";text="放大窗口试试，aardio 支持自适应缩放以及高分屏自动缩�?;left=20;top=269;right=377;bottom=293;db=1;dr=1;transparent=1;z=4}
)
/*}}*/

import com.lite;

/*
支持内存加载�?COM 控件可以写为
com.lite($"ocx �?dll 文件路径") ，发布后就不需要原 OCX 了�?
aardio 可以免注册调�?VB6 写的 OCX，但 VB 控件不支持内存加载�?可以在发�?EXE 完成界面可以点『转换为独立 EXE』按钮�?*/
var dll = com.lite("\.vb6\Vb6Control.ocx")

/*
创建VB控件,返回�?vbCtrl 是控件容�?vbCtrl._object 才是 COM 控件,
dll.createEmbedEx() 函数会自动将 vbCtrl 转换为可代理访问 vbCtrl._object 的代理对�?*/
var vbCtrl = dll.createEmbedEx(winform.static );//可选在参数@2中指定GUID,不指定也可以自己找到
winform.edit.print( dll.firstCoClassId() ); //可用这个函数查询 VB6 控件�?CLSID

//控件容器也是默认�?COM 事件监听�?如下直接指定响应 COM 事件的函�?vbCtrl.OnImageClick = function(value){
    winform.edit.print("VB控件里点击了图像,事件参数:"+value)

    //VB里这个事件的参数声明�?ByRef,所以添加返回值可以修改参�?    return 100
}

//修改VB控件的属�?vbCtrl.Picture = com.picture.loadObject( "~/example/Graphics/.gdip.jpg" )
/*
VB6 字符串虽存为 Unicode 编码，但却被设计为编�?ANSI 编码的程序，
VB的IDE，源码也都是 ANSI 编码，因�?Unicode 字符传入 VB 会变成乱码�?再例如文件路径里有简体中文，在繁体系统上就会导致 VB 组件异常或崩溃，
所以前面我们用 aardio 加载图像，文本或文件路径尽量不要�?VB 中处理�?*/

//修改VB控件的参数化属�?加上 set 前缀以函数形式调�?vbCtrl.setTestProperty(2,123)

/*
带多个参数的属性加上get前缀并以函数形式调用，例如：
*/
var testProperty = vbCtrl.getTestProperty(2);
winform.edit.print("VB 控件 TestProperty(2) 属�?",testProperty);

//调用 VB 函数
//纯函数规则：在返回值里接收输出参数，有几个输出参数就增加几个返回值�?var ret,outStr = vbCtrl.GetOutStr("");
winform.edit.print("调用 VB 控件函数返回�?",ret,outStr);

winform.edit.print("请点击图像试�?);

//调用 VB 函数，aardio 对象可以直接作为参数传给 VB
vbCtrl.CallAnything({
    Name = "aardio";
    Log = function(str){
        //VB  中访�? obj.Log  也会自动调自  obj.Log()
        if(str === null ) return;

        winform.msgbox(str,"�?VB 中可以直接调�?aardio 对象")
    }
})

winform.btnOpenVbp.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    }
})
winform.btnOpenVbp.oncommand = function(id,event){
    import process;
    process.exploreSelect("\.vb6\ocx.vbp")
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/VB/ocx.control.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/VB/ocx.control.md')

