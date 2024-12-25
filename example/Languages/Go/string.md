[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言之字符串操作

```aardio aardio
//aardio 调用 Go 语言之字符串操作
import golang;
var go = golang();

go.main = /**********
package main

import "C"
import "fmt"

//export TestString
func TestString(str  string)  {
    fmt.Printf("Go 直接收到 aardio 字符�? %s!\n",  str) ;
}

//export TestStringPtr
func TestStringPtr(str *string)  {
    fmt.Printf("Go 通过 *string 收到 aardio 字符�? %s!\n",  *str) ;
    *str = "这是新的字符�?;
}

//export TestCCharPtr
func TestCCharPtr(pStr *C.char) {

    //aardio 字符串指针转换为 Go 字符�?    var str = C.GoString(pStr);

    //Go 包公开的函数首字母必须是大写�?    fmt.Printf("Go 通过 *C.char 收到 aardio 字符�? %s\n", str)
}

func main() {}
**********/

go.buildShared("/.go/TestString.go");

//------------------下面调用 DLL-----------------------

import console.int;
var goDll = raw.loadDll("/.go/TestString.dll",,"cdecl");

/*
传一个字符串 + 一个字符串长度�?2 个参数就等价�?Go 中一�?string 类型参数
*/
var str = "2 个参数就等价�?Go 中一�?string 类型参数"
goDll.TestString(str,#str);//不要�?Go 中保�?aardio 传过去的字符�?
//创建 Go 字符串结构体
import golang.string;
var goStr = golang.string("这是 aardio 字符串，UTF-8 编码");

//�?Go 里这个参数应当声明为 *string 指针类型（aardio 结构体总是传址�?goDll.TestStringPtr(goStr);//不要�?Go 中保�?aardio 传过去的字符�?
/*
如果 Go 代码里修改了字符串�?那么在调用后应立即转换为 aardio 字符串（因为 Go 会回收内存）�?只要转换一次，golang.string 内部就会重新指向 aardio 分配的内存�?*/
var str = tostring(goStr);
console.log(goStr,str);

//�?C 指针，这是原始的方法
goDll.TestCCharPtr("这是 aardio 字符串，UTF-8 编码");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/string.md)

