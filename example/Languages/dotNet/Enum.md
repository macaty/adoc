[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: �?aardio 中使�?.NET 枚举（enum�?
```aardio aardio
//�?aardio 中使�?.NET 枚举（enum�?import console;
import dotNet;
var compiler = dotNet.createCompiler("C#");
compiler.Source = /***
namespace CSharpLibrary
{
    public class Object
    {
        public enum HardwareType
        {
            Mainboard, SuperIO, CPU, RAM, GpuNvidia, GpuAti, TBalancer, Heatmaster, HDD
        }

        public static HardwareType TestEnum(HardwareType v)
        {
             return v;
        }
    }
}
***/

compiler.import("CSharpLibrary");

//调用 C# 函数，枚举参数传数值，C# 不会报找不到函数错误，因�?aardio 会自动将其转换为参数所需的枚举类�?var ret = CSharpLibrary.Object.TestEnum(1);

//Enum 其实就是 int 类型�?32 位整数，aardio 整数默认就是这个类型
console.log(ret);

//也支持像下面这样直接访问枚举类型�?console.log( CSharpLibrary.Object.HardwareType.GpuAti );
/***
直接写数值速度更快，可以将枚举名写到注释里，例�?5/*HardwareType.GpuAti*/
那种没事把枚举值顺序改来改去的组件非常罕见�?但也是有�?�?当然，aardio 会记录解析的枚举值，所以不会重复解析�?***/

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Enum.md)

