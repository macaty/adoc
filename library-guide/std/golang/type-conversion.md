[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# Go / aardio 原生类型转换

aardio 可以使用 table 定义结构�?struct)，在结构体中可以定义原生类型�?
请参考：

- [raw 库](../../builtin/raw/api.html)
- [原生数据类型](../../builtin/raw/datatype.html)

## aardio，C 语言，cgo，Go 类型对应关系

aardioC 语言cgoGoBYTEcharC.charbyte,boolbytesinged charC.scharint8BYTEunsigned charC.ucharuint8,bytewordshortC.shortint16WORDunsigned shortC.ushortuint16intintC.intint32,runeINTunsigned intC.uintuint32intlongC.longint32INTunsigned longC.ulonguint32longlong longC.longlongint64LONGunsigned long longC.ulonglonguint64floatfloatC.floatfloat32doubledoubleC.doublefloat64INTsize\_tC.size\_tuintpointervoid \*unsafe.Pointer

要特别注�?Go �?bool 类型只有 1 个字节，相当�?aardio 中的 BYTE，�?aardio 中的 bool 类型则是 32 �?4 个字节，相当�?WinAPI 定义�?BOOL 类型�?
aardio 调用 Go 示例，首先调�?Go 编译器生�?DLL 文件�?
```aardio aardio
//调用编译后的 DLL 不需要导入此�?import golang;

//创建 Go 编译器（ 仅仅调用编译后的 DLL 不需�?）�?var go = golang();

//Go 源码：与 aardio 一样默�?UTF-8 编码
go.main = /**********
package main

import "C" //单独导入这句启用 CGO
import "fmt" //https://pkg.go.dev/fmt
import "unsafe" //https://pkg.go.dev/unsafe

type MyStruct struct {
    Int8Field   int8
    Int16Field  int16
    Int32Field  int32
    Int64Field  int64
    UintField   uint
    Uint8Field  uint8
    Uint16Field uint16
    Uint32Field uint32
    Uint64Field uint64
    Float32Field float32
    Float64Field float64
    pStr *C.char
}

//在注释里�?export 声明�?DLL 导出函数
//export SetStruct
func SetStruct(p uintptr) {
    // aardio 结构体转换为 Go 结构�?    st := (*MyStruct)(unsafe.Pointer(p))
    st.Int8Field = 8

    //Go �?fmt.Println 打印变量很方便，可传入多个任意类型的参数�?    fmt.Println( "�?Go 中打印结构体�?,st );

    var str = C.GoString(st.pStr);
    fmt.Printf("Go says: %s!\n", str)
}

//初始化函数，可以重复写多�?func init() { }

//必须写个空的入口函数，实际不会执�?func main() {}
**********/

//上面�?go.main 会自动保存到文件，然后编�?Go 源码生成同名 DLL 文件
go.buildShared("/.go/testStruct.go");

```

然后�?aardio 中调用上面生成的 DLL:

```aardio aardio
import console.int;
//加载 Go 编译�?DLL，注意要指定 cdecl 调用约定�?var goDll = raw.loadDll($"/.go/testStruct.dll",,"cdecl");
//如果已经生成 DLL，用$操作符可以嵌�?DLL 到代码中实现内存加载（发布后不需要带 DLL 文件）�?//声明结构�?class myStruct {
    byte Int8Field;//Go类型 int8
    word Int16Field;//Go类型 int16
    int32 Int32Field;//Go类型 int32
    long64 Int64Field;//Go类型 int64
    BYTE Uint8Field;//Go类型 uint8
    WORD Uint16Field;//Go类型 uint16
    INT32 Uint32Field;//Go类型 uint32
    LONG64 Uint64Field;//Go类型 uint64
    float Float32Field;//Go类型 float32
    double Float64Field;//Go类型 float64
    string pStr = "这是 aardio 字符�?
}

//创建结构�?var struct = myStruct();

//调用 Go 函数，传结构体（结构体总是传址�?goDll.SetStruct(struct);

//打印结构�?console.dumpJson(struct);

```

调用 Go 写的 DLL 请注意：

1. 加载 Go 写的 DLL 然后迅速（几秒以内）退出，Go 程序可能会崩溃�?

   这不是因为你写的代码有任何问题，而是 Go 需要额外启动运行时，无法应付这种快速退出的情况�?

   这时在后面加一�?thread.delay(2000) 就可以解决�?
   实际上除了写测试代码，一般也不会打开一个程序就在几秒内退出�?

   所以稍加注意一下，避免这个问题并不难�?
   只有 Go 写的 DLL 有这个问题，其他语言写的 DLL 没这种问题�?
2. 在同一个进程内�?Go 写的同一�?DLL 应当只加载一次�?

   当然�?DLL 没有卸载前，反复调用 raw.loadDll() 只是增加引用计数，不会重复加�?DLL�?
   如果多线程内存加载同一�?Go 写的 DLL 就会加载多个不同的副本�?

   这时候务必在 raw.loadDll("go.dll","共享名称") 的第 2 个参数指定共享名称，以避免重复加载�?
3. 要注意在 aardio �?DLL 不应当作为线程参数传递，实际上也没必要这样做�?
   只要�?raw.loadDll() 加载同名 DLL (或加载相同共享名称的内存 DLL) 是不会重复加载的�?

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/golang/type-conversion.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/golang/type-conversion.md')

