[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 加载 .NET 程序集（DLL�?
```aardio aardio
//aardio 加载 .NET 程序集（DLL�?import console;
import dotNet;

//查找并导�?.NET 程序�?DLL文件),参数可以是程序集名或者文件路径�?//默认会搜索系统目录、应用程序目录、或 "/bin/" 目录下的程序集�?var assembly = dotNet.load("CSNET2ClassLibrary");
console.log("程序集全�?,assembly.FullName);
console.log("程序集路�?,assembly.Location);

//dotNet.load 会调�?dotNet.reference 将参数@1指定的程序集名绑定参数@2指定的内存数据�?//参数 @2 在文件路径前�?$表示将文件编译到代码中并自内存加�?发布后不再需要该 DLL)
//这样就可以自内存加载程序集，并且其他 .NET 代码也可以通过程序集名称加载该程序集�?var assembly = dotNet.load("CSNET2ClassLibrary",$"\CSNET2ClassLibrary.dll");

//导入程序集中的名字空间或类，
//记住 .NET 里名字空间或类首字符大写，aardio 名字空间与类名一般小写首字符�?assembly.import("CSNET2ClassLibrary");

//程序集和名字空间相同时，也可以用 dotNet.import 加载程序�?+ 导入名字空间�?dotNet.import("CSNET2ClassLibrary");//可选用参数 @2 指定要加载的程序集名�?
//�?CSNET2ClassLibrary 名字空间下面的类构造对象实例，对象实例建议首字符小�?var simpleObject = CSNET2ClassLibrary.CSSimpleObject()

//修改 .NET 对象的属性�?simpleObject.FloatProperty = 936;

//获取 .NET 对象的属性�?console.log(simpleObject.FloatProperty);

//调用对象的静态方�?console.log( simpleObject.GetStringLength("HelloWorld")  );

//也可以通过类调用静态方�?效果跟上面一句是一样的
console.log( CSNET2ClassLibrary.CSSimpleObject.GetStringLength("HelloWorld")  );

console.pause();

/****
CSNET2ClassLibrary.dll �?C#源码如下�?
using System;
using System.Runtime.InteropServices;
namespace CSNET2ClassLibrary
{
    public class CSSimpleObject
    {
        private float fField = 13456.78f;

        public static int GetStringLength(string str)
        {
            return str.Length;
        }

        public float FloatProperty
        {
            get
            {
                return this.fField;
            }
            set
            {
                this.fField = value;
            }
        }
    }
}
****/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/loadFile.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/loadFile.md')

