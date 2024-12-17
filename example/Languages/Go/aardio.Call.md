[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Go 使用 aardio.Call 回调 aardio 窗口函数

```aardio aardio
//aardio 调用 Go 语言 - aardio.Call
import golang;
var go = golang();

go.main = /**********
package main

import "C"
import "aardio" //源文�? ~\lib\golang\.res\aardio\aardio.go

//export TestCallBack
func TestCallBack(hwnd uintptr){

    /*
    参数 hwnd �?aardio 窗口句柄
    "onSendJson" 用于指定 aardio 窗口对象成员函数�?    可指定不定个数调用参数，细节请参�?golang 扩展库中 aardio.Call 函数源码�?
    aardio.Call 的原理是发�?_WM_THREAD_CALLBACK 消息�?aardio 窗口�?    然后将参数用 JSON 编码发送给 aardio ，aardio 接收到消息后�?JSON 解析获得参数列表�?    然后自动转换为函数调用，可选返回数值或 null 值�?
    这种方法支持跨线程，类似�?RPC 调用（当然速度更快），
    没有跨线程的种种限制（不用理�?Go �?GMP 调度）�?    */
    aardio.Call(hwnd,"onSendJson","参数1","参数2");
}

func main() {}
**********/

//上面�?go.main 会自动保存到文件，然后编�?Go 源码生成同名 DLL 文件
go.buildShared("/.go/msgCallback.go");

//------------------下面调用 DLL-----------------------

import win.ui;
/*DSG{{*/
var winform = win.form(text="Go 使用 aardio.Call 回调 aardio 窗口函数";right=759;bottom=437)
winform.add(
edit={cls="edit";left=43;top=27;right=717;bottom=400;edge=1;multiline=1;z=1}
)
/*}}*/

winform.onSendJson = function(param1,param2){
    winform.edit.print("Go 调用�?aardio 函数，参数：",param1,param2)
}

//加载 Go 编译�?DLL，注意要指定 cdecl 调用约定
var goDll = raw.loadDll("/.go/msgCallback.dll",,"cdecl");
goDll.TestCallBack( winform.hwnd );

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/aardio.Call.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/aardio.Call.md')

