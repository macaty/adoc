[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 .NET 创建自定义控�?
```aardio aardio
//aardio 调用 .NET 创建自定义控�?import dotNet;
var compiler = dotNet.createCompiler("C#");
compiler.Reference("System.Drawing.dll","System.Data.dll","System.Windows.Forms.dll");
compiler.addSource("/0.WindowsFormsApp1.cs");
compiler.import("WindowsFormsApp1");

import win.ui;
import win.ui.ctrl.metaProperty;
/*
实际开发创建一�?win.ui.ctrl.netform 的库就行�?窗口控件都在 win.ui.ctrl 名字空间下，参考教�? https://mp.weixin.qq.com/s/s95LlTis3lrVeD8EYNZD0w
*/
namespace win.ui.ctrl{

    class netform {
        ctor(parent,tParam){

            //创建 .NET 窗口
            this.form = ..WindowsFormsApp1.Form1();

            //作为控件嵌入 aardio 窗口
            ..dotNet.setParent(this.form,parent,false);

            //aardio 控件必须�?hwnd 属性中指定窗口句柄
            this.hwnd = this.form.Handle;

            //.NET 使用 GDI+ / ARGB 格式颜色�?            this.form.BackColor = ..gdi.argbReverse(tParam.bgcolor);

            //添加委托回调
            this.form.onButton1Click = function(){
                if( this.oncommand ) this.oncommand();
            }
        }

        @_metaProperty; //控件元表,定义了控件的公用方法
    }

    namespace netform{
        _metaProperty = ..win.ui.ctrl.metaProperty(
            //添加控件函数
            setButtonText = function(txt){
                //类外部定义元属性时使用 owner 代替 this
                owner.form.button1.Text = txt;
            }
        );
    }
}

//下面在自定义控件的类名里�?"netform" 就可以了
/*DSG{{*/
var winform = win.form(text="aardio form";right=1047;bottom=634;bgcolor=10789024)
winform.add(
netform={cls="netform";text="自定义控�?;left=26;top=23;right=799;bottom=416;bgcolor=16777215;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

winform.netform.oncommand = function(id,event){
    winform.msgbox("点击�?C# �?aardio 窗口里创建的按钮，在 C# 中调�?aardio 函数�?);
    winform.netform.setButtonText("点击�?C# 创建的按�?);
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Control/custom.md)

