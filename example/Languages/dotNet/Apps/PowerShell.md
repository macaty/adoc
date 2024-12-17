[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 PowerShell

```aardio aardio
//aardio 调用 PowerShell
import win;
import console;
import dotNet.ps;

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

    # PowerShell 会把所有语句的默认输出塞进返回值，改为赋值语句可避免这个问题
    $temp = $win.InvokeMember("msgbox","事件被回调了",$str)

    # return 语句只能改最后一个返回值，与其他语言有较大区�?    return $a
})

$obj.Test()
`,{win = dotNet.ps.export(win)});

console.log(out,err);
console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/PowerShell.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/PowerShell.md')

