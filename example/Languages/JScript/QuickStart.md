[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 入门

```aardio aardio
//入门
import console;
import web.script;

//创建 JScript 脚本虚拟�?var   = web.script("JScript")

//直接�?aardio 对象（表、数组、函数）赋值为 vm 的成员，即可�?JScript 中直接调用�?vm.external = {
    add = function(a,b,c){
        return a + b + c;
    };
    log = function(...){
        console.log(...);
    };
}

/*
JavaScript 快速入门：
https://quickref.me/zh-CN/docs/javascript.html
https://learnxinyminutes.com/docs/zh-cn/javascript-cn/
*/

//加载 JScript,也可以用 vm.doScript() 函数加载脚本
vm.script = /*****
function TestFunction(a,b) {
    //创建 COM 对象
    var shell = new ActiveXObject("Shell.Application")
    var ns = shell.NameSpace("::{7007ACC7-3202-11D1-AAD2-00805FC1270E}")

    var it = new Enumerator(ns.Items())
    for ( ; !it.atEnd(); it.moveNext()){
        var item = it.item();
        external.log(item.Name,item.Path);
    }

    var arr = new VBArray(a).toArray();
    return external.add(arr[0],arr[1],b);
}
*****/

//通过 vm.script.函数�?) 调用 JScript 函数�?var ret = vm.script.TestFunction({12,23},1);
console.log( ret );

//执行并计�?JScript 表达式代�?返回表达式的�?console.log( vm.eval("1+1") )

//也可以直接调用下面的函数计算 JScript 表达式的值，例如获取 JScript 版本�?var version = web.script.eval(`ScriptEngine()
    + " " + ScriptEngineMajorVersion()
    + "."  + ScriptEngineMinorVersion()
    + "."  + ScriptEngineBuildVersion()
    `)
console.log(version);

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/JScript/QuickStart.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/JScript/QuickStart.md')

