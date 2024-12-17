[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言入门

```aardio aardio
//aardio 调用 Go 语言入门
/*
Go 语言文档教程:
https://www.aardio.com/zh-cn/doc/library-guide/std/golang/type-conversion.html
https://quickref.me/zh-CN/docs/golang.html
https://learnxinyminutes.com/docs/zh-cn/go-cn
https://pkg.go.dev/builtin
https://go.dev/play
*/

//调用编译后的 DLL 不需要导�?golang
import golang;

//创建 Go 编译器�?var go = golang();

//Go �?aardio 源码都是 UTF-8 编码
go.main = /**********
package main

import "C" /* 启用 CGO�?这句代码前面的注释会作为 C 语言代码编译（或编写 #cgo 指令），
如果在这句代码前面写普通注释编译器会闪退�?*/

//下面这句注释指令导出 DLL 函数
//export Add
func Add(a int32,b int32) int32{

    //aardio 中整数默认为 int32 类型，小数默认为 double 类型
    return a + b;
}

/*
aardio，C 语言，cgo，Go 类型对应关系如下�?
aardio | C 语言              | cgo         | Go
BYTE   | char                | C.char      | byte,bool
byte   | singed char         | C.schar     | int8
BYTE   | unsigned char       | C.uchar     | uint8,byte
word   | short               | C.short     | int16
WORD   | unsigned short      | C.ushort    | uint16
int    | int                 | C.int       | int32,rune
INT    | unsigned int        | C.uint      | uint32
int    | long                | C.long      | int32
INT    | unsigned long       | C.ulong     | uint32
long   | long long           | C.longlong  | int64
LONG   | unsigned long long  | C.ulonglong | uint64
float  | float               | C.float     | float32
double | double              | C.double    | float64
INT    | size_t              | C.size_t    | uint
pointer| void *              |             | unsafe.Pointer

上面�?aardio 类型指的是『原生类型�?
https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/datatype.html

aardio 中的数值类型以小写表示有符号，大写表示无符号�?Go 中的 uintptr 也可以表示指针（pointer）�?*/

//初始化函数，可以重复写多�?func init() {}

//必须写个空的入口函数，实际不会执�?func main() {}
**********/

//编译 Go 源码生成同名 DLL 文件，go.main 会自动保存参数指定的文件
go.buildShared("/.go/start.go");

//------------------下面调用 DLL-----------------------

//加载 Go 编译�?DLL，注意要指定 cdecl 调用约定�?var goDll = raw.loadDll("/.go/start.dll",,"cdecl");
//生成 DL后改�?$"/start.dll" 可内存加载（发布后不用带 DLL）�?
/*
免声明直接调�?DLL 函数�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/directCall.html
*/
var c = goDll.Add(2,3);

//也可以先声明 API，明确指定参数与返回值类�?var add = goDll.api("Add","int(int a,int b)" );
var c = add(2,3);

import console.int;
console.log(c);

//------------------必读！避坑说明！----------------------

/*
以下�?Go 一直存在且一直没解决的一个问题，不是 aardio 的锅�?而且只有 Go 写的 DLL 有这个问题，其他语言写的 DLL 没这种问题�?
Go 写的 DLL 卸载时的收尾工作做得很糟糕，可能出现莫名其妙的崩溃和闪退问题�?遇到这种问题，一定要先检查是不是调用�?Go 写的 DLL�?
然后按下面的步骤处理，基本可以避免问题�?
1�?Go 写的 DLL 必须在主线程加载一次，最后不要释�?DLL 然后再次加载�?�?DLL 没有卸载前，反复调用 raw.loadDll() 只是增加引用计数，不会重复加�?DLL�?
但内存加�?DLL 且不指定共享名称就会加载多个不同的副本，这会导致前面说的崩溃问题�?这时候必须在 raw.loadDll("go.dll","共享名称") 的第 2 个参数指定多线程共享名称，以避免重复加载�?并且首先在主线程加载一次该 DLL 且不要释放，这样工作线程加载内存 DLL 只是增加引用计数，不会重复加载�?
2、主线程加载Go 写的 DLL 然后迅速（几秒以内）退出，Go 程序可能会崩溃�?这时在后面加一�?thread.delay(2000) 就可以解决�?
实际上除了写测试代码，一般也不会打开一个程序就在几秒内退出�?所以稍加注意一下，避免这个问题并不难�?
3、要注意�?aardio �?DLL 不应当作为线程参数传递，实际上也没必要这样做�?*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/go.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/go.md')

