[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: JSON 扩展

```aardio aardio
//JSON 扩展
import console;
import web.script.json;

//创建 JScript 解释�?var vm = web.script();

//添加脚本，多次写入此属性是添加脚本不是覆盖替换脚本
vm.script = /*
function test(data) {
    //return JSON.stringify(data); // 已自动引�?JSON3
    return [data[1],data[2]];
}

var obj = {test:test}
*/

var aardioArray = {
    {50,80};
    {20,24};
    {100,103};
    {4,8};
}

/*
通过 vm.json.test 调用 JS 函数，作用与调用 vm.script.test 类似�?�?vm.json.test 会自动使�?JSON 转换参数与返回值，因此可以传输 JSON 支持的所有对象�?*/
var ret = vm.json.test( aardioArray );

//如果JS 函数名包�?. 号这样写�?var ret = vm.json["obj.test"]( aardioArray );

/*
之所以不允许 vm.json.obj.test() 这种�?JS 函数名中直接包含点号的写法，
是为了避免不必要的混淆，不能�?vm.json.obj 理解�?vm.script.obj 这样�?JS 对象�?
vm.json 本质�?vm.eval + JSON  的语法糖，调用、传参、取返回值都要随时明确这一点�?例如你不能将 vm.json.xxx 作为 JS 对象传入 JS 函数�?更不能在 vm.json.xxx() 参数中传入一�?JS 对象�?*/

//这个下标里可以写返回 JS 函数�?JS 表达式，这样就很灵活了，例如�?var ret = vm.json["(function() { return obj.test; })()"]( {50,80} );

//使用 vm.json() �?aardio 对象转换�?JS 对象�?var jsArray = vm.script.obj.test( vm.json(aardioArray) )
//上面�?vm.script.obj 是真正的 JS 对象，参数可以使�?JS 对象�?
//使用 vm.json() �?JS 对象转换�?aardio 对象
console.dump( vm.json(jsArray) );

console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/JScript/json.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/JScript/json.md')

