[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 入门

```aardio aardio
//入门
import console;
import web.script;

//创建 VBScript 虚拟�?var vm = web.script("VBScript")

//直接�?aardio 对象（表、数组、函数）赋值为 vm 的成员，即可�?VBScript 中直接调用�?vm.external = {
    add = function(a,b){
        return a + b;
    };
}

//模拟 WScript 对象
vm.WScript = {
    CreateObject = ..com.CreateObject;
    GetObject = ..com.GetObject;
    Echo = function(...){
        console.log(...);
    };
}

//加载 VBScript,也可以用 vm.doScript() 函数加载脚本�?vm.script = /*
Function TestFunction(a,b)
    Dim shell, ns, item

    '创建 COM 对象
    Set shell = CreateObject("Shell.Application")
    Set ns = shell.NameSpace("::{7007ACC7-3202-11D1-AAD2-00805FC1270E}")

    '遍历 COM 对象
    For Each item In ns.Items()
        '注意 VBScript 调用方法且不接收返回值时，不要加括号�?         WScript.Echo item.Name,item.Path
    Next

   TestFunction = external.add(a(0),b(0))
End Function
*/

//通过 vm.script.函数�?) 调用 VBScript 函数�?var ret = vm.script.TestFunction({12,13},{2,3});
console.log( ret );

//执行并计�?VBScript 表达式代�?返回表达式的�?var version = vm.eval(`ScriptEngine() & " " & ScriptEngineMajorVersion()& "."  & ScriptEngineMinorVersion() & "."  & ScriptEngineBuildVersion()`);

console.log(version);
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/VBScript/QuickStart.md)

