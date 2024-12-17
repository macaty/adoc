[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?Delphi 语言�?aardio 编写控件

```aardio aardio
//Delphi 控件
import win.ui;
/*检测DLL{{*/
if(!io.exist("\Project1.dll")){
    import process;
    process.exploreSelect("\Project1.dpr");
    error("请先�?Delphi 打开此目录下�?DLL 源码工程编译生成 \Project1.dll")
}
/*}}*/

//改为 raw.loadDll($"\Project1.dll") 表示嵌入 DLL 到代码并通过内存加载
var delphiDll = raw.loadDll("\Project1.dll");
class win.ui.ctrl.delphiForm{
    ctor(parent,tParam){
        /*
        aardio 可以免声明直接调�?API 函数（当然先声明API也是可以的，先声明可以支持更多的参数类型），
        所有结构体(传址)、字符串、字节数�?raw.buffer)、不大于32位的整数�?4位无符号整数（math.size64�?        都可以直接作为调用参数，不需要指定类型，更可通过尾标语法指定返回值的类型以及是否对字符串进行 UTF-16 自动转换�?
        相关范例：�?aardio 范例 / 调用其他语言 / C语言 �?        相关文档�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
        */
        this.hwnd = delphiDll.CreateForm(parent.hwnd);
    };
    @..win.ui.ctrl.metaProperty()
}
/*DSG{{*/
var winform = win.form(text="�?Delphi 语言�?aardio 编写控件";right=507;bottom=423;bgcolor=11842740)
winform.add(
custom={cls="delphiForm";text="嵌入 Delphi 控件";left=17;top=28;right=490;bottom=211;db=1;dl=1;dr=1;dt=1;z=1};
edit={cls="edit";text="请先�?Delphi 打开此目录下�?DLL 源码工程编译生成 \Project1.dll";left=16;top=228;right=489;bottom=398;edge=1;multiline=1;z=2}
)
/*}}*/

import web.json;
winform.onTest = function(delphiStructParam){
    winform.edit.print("Delphi 调用了aardio 函数,参数如下:");
    winform.edit.print(delphiStructParam);
    delphiStructParam.x = 90;

    //可选返回修改后的结构体
    return delphiStructParam;
}
winform.edit.text = "";

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Delphi/dll.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Delphi/dll.md')

