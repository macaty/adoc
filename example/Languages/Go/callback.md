[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - 回调函数

```aardio aardio
//aardio 调用 Go 语言 - 回调函数
import golang;
var go = golang();

go.main = /**********
package main

/*
typedef int _stdcall (*addCallBack)(int a,int b);

//�?C 函数回调 aardio 函数
static int callAddCallBack(void* fnAdd,int a,int b){
    return ((addCallBack)fnAdd)(a,b);
}
*/
import "C" //C 代码写在这一句前�?import "unsafe"

//export TestCallBack
func TestCallBack(fnCallback unsafe.Pointer) int{

    //�?C 函数回调 aardio 函数，改�?aardio.callPtr() 更简单一些�?    var r = C.callAddCallBack(fnCallback,123,2)

    //C.int 转换�?Go 类型�?int
    return int(r)
}

func main() {}
**********/

go.buildShared("/.go/cgoCallback.go");

//------------------下面调用 DLL-----------------------
import console.int;

//加载 Go 编译�?DLL
var goDll = raw.loadDll("/.go/cgoCallback.dll",,"cdecl");

/*
创建 C 回调函数指针�?文档:  https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/callback.html

注意：aardio �?Go 导出函数所在的默认 goroutine
之间的互调属于同一线程（这里不用考虑多线程），不必使�?thread.tostdcall）�?*/
var callback = raw.tostdcall(
    function(a,b){
        return a+b;
    },"int(int a,int b)");

var ret  = goDll.TestCallBack( callback )

console.log(ret);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/callback.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/callback.md')

