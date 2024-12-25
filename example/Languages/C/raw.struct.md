[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 C 语言之静态内存结构体

```aardio aardio
//aardio 调用 C 语言之静态内存结构体
//相关范例: file://~/example/aardio/Raw/raw.struct.aardio

import console.int;
import tcc;

var code = /**
# include <stdlib.h>

typedef struct {
    int number;
} TestSturct;

__declspec(dllexport) void test(int len, TestSturct* pStruct[]) {

    for (int index = 0; index < len; index++)
    {
        pStruct[index]->number = 123;
    }
}
**/
var c = tcc();
c.compile(code);

import raw.struct;

//创建『静态内存结构体�?testSturct = raw.struct({
    int number;
});

/*
aardio 结构体在与原�?API 交互时动态分配内存指针�?但『静态内存结构体』可以分配固定不变的内存指针，调用原�?API 时不需要再动态分配内存�?�?aardio 中读写静态内存结构体的直接成员（不包含成员的成员）会更慢�?*/

//创建『静态内存结构体』指针数�?var array = { testSturct(); testSturct(); }

//调用 API，『静态内存结构体』可用于 pointer 指针类型�?c.test(2, {pointer items[2] = array } );

//输出值，可以看到 iNumber 已经�?C 语言改掉�?console.log( array[1].number  );

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/C/raw.struct.md)

