[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 内存加载 .NET 程序集（DLL�?
```aardio aardio
//aardio 内存加载 .NET 程序集（DLL�?import console.int;
import dotNet;

/*
在『虚拟程序集引用表』注册一个或多个虚拟程序集，
这些虚拟程序集可以是内存程序集、本地程序集、EXE 内嵌资源中的程序集�?
aardio 加载�?.NET 程序找不到程序集（DLL）时�?会查找『虚拟程序集引用表』并加载已注册的虚拟 DLL

可用�?aardio 工具 / 转找工具 / .NET 引用表转�?』自动生成下面的代码�?*/
dotNet.reference({
    //「键」为程序集短名称�?DLL 文件�?）�?    //「值」为程序集内存数据或文件路径（支持内嵌资源路径），也可以是一个返回所需值的函数�?
    //虚拟 CSNET2ClassLibrary.dll
    "CSNET2ClassLibrary" = $"\CSNET2ClassLibrary.dll";

    //虚拟 A.B.C.dll
    "A.B.C" = $"\CSNET2ClassLibrary.dll";
})

//加载上面的虚拟程序集（也可以利用上面的方法添加依�?DLL ）�?var assembly = dotNet.load("CSNET2ClassLibrary");

//可以直接在参�?@2 里写 DLL 内存数据或文件路径（自动调用 dotNet.reference）�?var assembly = dotNet.load("CSNET2ClassLibrary",$"\CSNET2ClassLibrary.dll");

//导入程序集中的名字空间或类�?//.NET 名字空间或类名建议首字符大写，aardio 类名建议首字符小写�?assembly.import("CSNET2ClassLibrary");

//调用 .NET 类的静态成员函�?var len =  CSNET2ClassLibrary.CSSimpleObject.GetStringLength("HelloWorld");
console.log( len );

//�?CSNET2ClassLibrary 名字空间下面的类构造对象实例，对象实例建议首字符小写�?var simpleObject = CSNET2ClassLibrary.CSSimpleObject()

//获取 .NET 对象的属性�?console.log( simpleObject.FloatProperty );

/*
也可以用 dotNet.loadFile() 函数自内存加载单�?DLL 文件�?但是 dotNet.loadFile() 并不支持 『虚拟程序集引用表』，无法添加依赖 DLL�?*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/reference.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/reference.md')

