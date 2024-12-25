[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 PowerShell 之共享应用域

```aardio aardio
//aardio 调用 PowerShell 之共享应用域
import win;
import console;
import dotNet.ps;
//aardio 调用 PowerShell 教程: https://mp.weixin.qq.com/s/Sr4HNkOJ1mmAj_V52v69IA

/*
dotNet.ps 在当前进程运�?PowerShell�?aardio / .Net(C#) / PowerShell 共享应用程序域，并共享导入的 .Net 程序集与类型�?*/
var compiler = dotNet.createCompiler("C#");
compiler.Source = /******
namespace CSharpLibrary
{
    public class Object
    {
        //定义一个委托类�?        public delegate int TestDelegateType(string str,int a);

        //定义一个事�?        public event TestDelegateType onTestEvent;

        public int Test()
        {
            return onTestEvent("你好",123);
        }

        //PowerShell 5 不需要加这个函数
        public static Object New(){return new Object(); }
    }
}
******/
compiler.import("CSharpLibrary"); //编译 C# 代码并导入名字空�?
var out,err = dotNet.ps( `
param($win) # 声明参数，类�?aardio �?$win = ...

#PowerShell �?:: 表示访问类的静态成员，New 用于创建对象
$obj = [CSharpLibrary.Object]::New() #低于 PowerShell 5 需要在类里增加 New 函数或改�?New-Object

# 添加事件，注意下面方括号里是强制类型转换
$obj.add_onTestEvent( {
    param($str,$a) # 声明参数

    # PowerShell 有个非常奇怪的规则，所有语句的默认输出会被塞进返回值，
    # return 语句并不能改变这个行为，如下改为赋值语句可避免 onTestEvent 报错返回值类型不匹配�?    $temp = $win.InvokeMember("msgbox","事件被回调了",$str)

    # return 语句只能改最后一个返回值，与其他语言有较大区�?    return $a
})

$obj.Test()
`,{ win = dotNet.ps.export(win) });

console.log(out,err);
console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/AppDomain.md)

