[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: JSON 扩展

```aardio aardio
//JSON 扩展
import console;
import web.script.json;
var vm = web.script("VBScript");

vm.external = {
    log = function(...){
        console.log(...);
    };
}

vm.script = /*
Function TestFunction()

    '调用 aardio 兼容JSON，JSONP，JSON5，部分类 YAML 语法�?web.json.parse() 函数
    Set jObject = JSON.parse("{name:{a:123:b:456,c:[1,2,3]}}" )
    jObject.newKey = "测试"

    arr = jObject.name.c
    arr(0) = "测试"

    '遍历 JSON 数组
    For Each item In arr
         external.log item
    Next

    TestFunction =  arr(0)
End Function
*/

//通过 vm.script.函数�?) 调用 VBScript 函数�?var ret = vm.script.TestFunction();
console.dump(ret);
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/VBScript/json.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/VBScript/json.md')

