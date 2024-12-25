[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 C 语言之原生数组操�?
```aardio aardio
//aardio 调用 C 语言之原生数组操�?import console;
import tcc;

var c = tcc();
c.code = /***
    #include <stdlib.h>
    __declspec(dllexport) void getArray(unsigned int a[],unsigned int b[] )
    {
            b[0] = a[1];
            b[1] = a[0];
    }
***/
c.output( "/getArray.dll" ); //生成DLL

//加载生成�?DLL，默认调用约�?cdecl
var dll = raw.loadDll( "/getArray.dll",,"cdecl" );

//方法一：免声明调用 C 函数，结构体为输出参数（ 增加到返回�?�?var ret,a,b = dll.getArray(

    //原生数组必须放到结构体里，结构体参数总是传址（这里指数组地址�?    //原生数组相关文档�?https://www.aardio.com/zh-cn/doc/library-guide/builtin/raw/struct.html#array
    { INT a[] = {123,456}},

    //注意 aardio 中以大写 INT 表示无符号数，小�?int 表示有符号数（可表示负数�?    { INT b[2] = {} }

);

//输出结果
console.dumpTable(b);

//方法二：声明 API
var getArray = dll.api("getArray","void(struct a,struct &b)");

//仅声明了一个输出参数，只有一个返回�?var b = getArray(
    { INT a[] = {123,456}},
    { INT b[2] = {} }
);

//输出结果
console.dumpTable(b);
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/C/array.md)

