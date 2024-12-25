[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用模板语法编译并运�?C\# 代码

```aardio aardio
//aardio 使用模板语法编译并运�?C# 代码
//dotNet.desktop 扩展库使用了这种技�?import win.version;
import dotNet;
var compiler = dotNet.createCompiler("C#");

//支持模板语法�?https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
compiler.Source = /***
?> //C#源码如果起始于本行前面的 aardio 模板标记则支持模板语�?namespace CSharpLibrary
{
    public class Object
    {
        <? if _WINXP { ?>
        public string Test(){
            return "Windows XP";
        }
        <? } else { ?>
        public string Test(){
            return "<?= win.version.name ?>";
        }
        <? } ?>
    }
}
***/

//编译内存程序集，导入名字空间
compiler.import("CSharpLibrary");

//使用 C# 编写的类构造对象实�?var netObj = CSharpLibrary.Object();

//调用实时编译的C#函数
var ret = netObj.Test();

import console;
console.log( ret );
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Advanced/template-compiler.md)

