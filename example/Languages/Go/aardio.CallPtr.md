[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - aardio.CallPtr

```aardio aardio
//aardio 调用 Go 语言 - aardio.CallPtr
import golang;
var go = golang();//创建 Go 编译器（ 仅调用编译的 DLL 不需要此扩展�?）�?
//Go �?aardio 一样，源码与字符串默认�?UTF-8 编码
go.main = /**********
package main

import "C"
import "unsafe"
import "aardio" //源文�? ~\lib\golang\.res\aardio\aardio.go

//export TestCallBack
func TestCallBack(fnCallback uintptr) int{

    var s = "字符�?

    /*
    回调 aardio �?raw.tostdcall 创建的函数指针�?    �?aardio.CallPtr 不需要指定参数个数，并支持可变参数（ 0 �?15 �?uintptr 类型参数 ）�?    返回值类型为 )(uintptr,uintptr,syscall.Errno)�?
    注意：aardio �?Go 导出函数所在的默认 goroutine 之间的互调属于同一线程（这里不用考虑多线程）�?    */
    var r,_,_ = aardio.CallPtr(fnCallback,uintptr(unsafe.Pointer(&s)),123 )

    //C.int 转换�?Go 类型�?int
    return int(r)
}

func main() {}
**********/

//上面�?go.main 会自动保存到文件，然后编�?Go 源码生成同名 DLL 文件
go.buildShared("/.go/CallPtr.go");

//------------------下面调用 DLL-----------------------

import console.int;

//加载 Go 编译�?DLL，注意要指定 cdecl 调用约定
var goDll = raw.loadDll("/.go/CallPtr.dll",,"cdecl");

//创建 C 回调函数指针，文�?  https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/callback.html
var callback = raw.tostdcall(
    function(goString,num){

        // Go 字符串实际是一个结构体，下面转换为 aardio 字符�?        var str = raw.tostring(goString.p,1,goString.n);
        console.log("回调参数:",str,num)

        return 123;
    },"int({ptr p;int n} goString,int num)");

var ret  = goDll.TestCallBack( callback )
console.log(ret);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/aardio.CallPtr.md)

