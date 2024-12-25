[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 .NET - 原生结构体操�?
```aardio aardio
//aardio 调用 .NET - 原生结构体操�?import dotNet;
import console.int;
console.open();

var compiler = dotNet.createCompiler("C#");

//指定 /unsafe 选项，否则操作原生结构体的代码会非常复杂
compiler.Parameters.CompilerOptions = "/optimize /unsafe" ;

compiler.Source = /******
using System;
using System.Runtime.InteropServices;

namespace CSharpLibrary
{
    //使用跨语言兼容的结构体内存布局
    [StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
    public unsafe struct MyCStruct //结构体前要加 unsafe 关键�?    {
        public int id;
        public float value;
    }

    public class Util
    {
        //函数名前要加 unsafe 关键�?        public static unsafe void TestStruct(IntPtr bytePtr)
        {
            //创建结构�?            MyCStruct myStruct;

            //将数据复制到结构�?            myStruct = *(MyCStruct*)bytePtr;

            System.Console.WriteLine("id:{0},value:{1}",myStruct.id,myStruct.value);

            //修改结构�?            myStruct.id = 33;
            myStruct.value = 44;

            //将修改后的内容写回去
            *(MyCStruct*)bytePtr = myStruct;
            //Marshal.StructureToPtr(myStruct,bytePtr,false);
        }

    }
}
******/
compiler.import("CSharpLibrary");

//声明结构�?class MyCStruct {
    int id = 22;
    float value = 33;
}

//创建结构�?var myStruct = MyCStruct();

//分配固定内存
var fixedBuffer = raw.buffer(myStruct);

//直接取指针地址要谨慎，务必保持 fixedBuffer 在作用域内（避免回收内存）�?//获取指针并转为数值（.NET 不能传指针参数，可以先换为数值）
var intPtr = tonumber( raw.toPointer(fixedBuffer) );

//结构体指针地址作为参数
CSharpLibrary.Util.TestStruct( intPtr ); //C# 参数声明�?IntPtr 类型（本质上也是数值）

//自内存获取为结构体�?raw.convert(fixedBuffer,myStruct);

//查看 C# 修改后结构体数据
console.dumpJson(myStruct);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/raw-struct.md)

