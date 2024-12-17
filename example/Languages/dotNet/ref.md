[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中引�?.NET 对象

```aardio aardio
//�?aardio 中引�?.NET 对象
import dotNet;
var compiler = dotNet.createCompiler("C#");//创建C#语言编译�?compiler.Source = /***
namespace CSharpLibrary
{
    public class Object
    {
        public static void Test(ref double num,int [] arr){
            num = 12.3;
            arr[0] = 56;
        }
    }
}
***/

compiler.import("CSharpLibrary"); //自程序集导入名字空间

/*
以下函数都可以创建创建原�?.NET 对象�?这些原生对象会被封包�?DispatchableObject 对象内以避免被自动转换为 aardio 对象�?
DispatchableObject 对象传入 aardio 会被自动封包�?dotNet.object 对象�?这些对象传回 .NET 会被自动解包为原�?.NET 对象�?
dotNet.object(value,byRef)
dotNet.byte(value,byRef)
dotNet.ubyte(value,byRef)
dotNet.word(value,byRef)
dotNet.uword(value,byRef)
dotNet.int(value,byRef)
dotNet.uint(value,byRef)
dotNet.long(value,byRef)
dotNet.ulong(value,byRef)
dotNet.float(value,byRef)
dotNet.double(value,byRef)

这些函数创建的对象保存了对原�?.NET 对象的引用，而非直接传值�?所以简单地将上述函数的�?@2 个参数设�?true 即可支持需要引�?.NET 原生对象的输出参数（ ref,out 参数�?
dotNet.buffer(size,value) 可直接创建封装为 dotNet.object 且支持引用传参的 buffer 对象�?*/

var num = dotNet.double(12.5,true);//创建 .NET 对象，返�?dotNet.object 对象而不是普通数值�?
//也可以创�?.NET 数组
var arr = dotNet.int({1,2,3}); //创建 .NET 对象，返�?dotNet.object 对象而不是普通数组�?
//调用函数, dotNet.object 对象可以直接作为 .NET 函数参数使用�?CSharpLibrary.Object.Test(num,arr);

import console;
console.log( arr[1] ) //�?aardio 中这种数组可用下标直接读写数组成员�?
//DispatchableObject 对象如果存储的是 Primitive,enum,string 类型或这些类型的普通数组则可使�?Value 属性读写原始�?console.log( num.Value );

//支持 tostring(),tonumber() 转换�?console.log(tostring(num),tonumber(num));

/*
DispatchableObject 对象可调�?byRef 函数设置是否传址�?ref,out 参数），
返回值为对象自身。不指定参数则返回一个表示当前传参设置是否为传址的布尔值�?*/
num.byRef(true)

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/ref.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/ref.md')

