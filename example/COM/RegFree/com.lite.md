[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 免注册调�?COM 控件

```aardio aardio
//免注册调�?COM 控件
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="免注册嵌�?VB 控件";right=700;bottom=266)
winform.add(
edit={cls="edit";left=356;top=20;right=665;bottom=243;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
static={cls="static";text="Static";left=21;top=20;right=330;bottom=243;dl=1;dt=1;transparent=1;z=1}
)
/*}}*/

import com.lite;
/*
支持内存加载�?COM 控件可以写为 com.lite($"ocx �?dll 文件路径") �?发布后就不需要原 OCX 了�?
不支持内存加载的 COM 控件�?也可在发布完成界面点击『转换为独立 EXE』按钮�?
可以免注册调�?VB6 写的 OCX，但 VB 控件不支持内存加载�?不支持免注册的控件也可以�?com.activeX.regsvr32 静默注册,不需要管理权限�?或�?com.activeX.appData() 释放�?appData 目录并且自动注册（发布后不需要原 OCX）�?*/
var dll = com.lite.appData("aardio\vb6\Vb6Control.ocx" //dll 后缀名也可以
    ,$"~/example/Languages/VB/.vb6/Vb6Control.ocx")

//不需要注册直接创建控�?不是内存 DLL可省略参数@2里指定的类名
var vbCtrl = dll.createEmbedEx(winform.static);

//响应 COM 事件
vbCtrl.OnImageClick = function(value){
    winform.edit.print("VB控件里点击了图像,事件参数:"+value)
    return 100; //VB里这个事件的参数声明�?ByRef,所以添加返回值可以修改参�?}

//修改 VB 控件的属�?vbCtrl.Picture = com.picture.loadObject( "~/example/Graphics/.gdip.jpg" )
winform.show();

//调用 VB 函数，aardio 对象可以直接作为参数传给 VB
vbCtrl.CallAnything({
    Name = "aardio";
    Log = function(str){
        //VB  中访�? obj.Log  也会自动调自  obj.Log()
        if(str === null ) return;

        //winform.msgbox(str,"�?VB 中可以直接调�?aardio 对象")
    }
})

winform.edit.print("请点击图像试�?);

win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/RegFree/com.lite.md)

