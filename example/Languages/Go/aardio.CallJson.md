[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - aardio.CallJson

```aardio aardio
//aardio 调用 Go 语言 - aardio.CallJson
import golang;
var go = golang();//创建 Go 编译器（ 仅调用编译的 DLL 不需要此扩展�?�?
//Go �?aardio 一样，源码与字符串默认�?UTF-8 编码
go.main = /**********
package main

import "C"
import "aardio" //源文�? ~\lib\golang\.res\aardio\aardio.go

//export TestCallBack
func TestCallBack(fnCallback uintptr) int{

    var s = "字符�?

    /*
    回调 aardio �?raw.jsonCall 创建的函数指针�?    支持可变参数（使�?JSON 自动转换参数），aardio 函数返回 null �?int 类型整数�?�?    aardio.CallJson() 返回类型�?(int,error)�?
    注意：aardio �?Go 导出函数所在的默认 goroutine 之间的互调属于同一线程（这里不用考虑多线程）�?    */
    var r,_ = aardio.CallJson(fnCallback,s,123,map[string]int{"id": 1, "id2": 2} )

    return r
}

func main() {}
**********/

//上面�?go.main 会自动保存到文件，然后编�?Go 源码生成同名 DLL 文件
go.buildShared("/.go/CallJson.go");

//------------------下面调用 DLL-----------------------

import console.int;

//加载 Go 编译�?DLL，注意要指定 cdecl 调用约定
var goDll = raw.loadDll("/.go/CallJson.dll",,"cdecl");

import  raw.jsonCall;

//创建回调函数指针�?�?Go 中必须用 aardio.CallJson 调用�?var callback = raw.jsonCall(
    function(a,b,c){
        console.log("回调参数:",a,b)
        console.dumpJson(c);
        return 123;
    } );

var ret  = goDll.TestCallBack( callback )
console.log(ret);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/aardio.CallJson.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/aardio.CallJson.md')

