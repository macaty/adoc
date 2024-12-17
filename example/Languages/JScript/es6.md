[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: ES6(Chakra)

```aardio aardio
//ES6(Chakra)
import console;
import web.script;
var chakra = web.script("ES6");

//Chakra 最低要求为 Win10/Win11�?Win7 已逐渐退出市场一般可以忽�?assert(_WIN10_LATER,"虽然低于 Win10 的系�?ES6 参数自动退化为 JScript，但此示例用到了 ES6 语法");

//导出 aardio 函数�?JavaScript
chakra.external = {
    log = function(...){
        console.log(...)
    }
}

chakra.script = /*****
external.log("JavaScript 调用 aardio 函数");

class ES5 {
    constructor(name) {
        this._name = name;
    }

    test() {
        let result = 0;
        let numbers = [1,2,3];

        if(Array.isArray(numbers)){
            numbers.forEach( (value) =>{
            result = result + value;
            });
        }

        return result;
    }
}

class ES6 extends ES5 {
  test(v) {
    return  super.test() + v;
  }
}

var es6 = new ES6();
var testResult = es6.test(1000);

var test = function(v){
    return es6.test(v);
}

*****/

//访问脚本中的变量
console.dump( chakra.script.testResult );

//通过 script 对象调用 JavaScript 函数，必须有参数，不支持无参数函�?console.dump( chakra.script.test(1000) );

//通过 json 对象调用 JavaScript 函数，参数与返回值使�?JSON 格式转换。调用参数要符合 JS 函数定义�?console.dump( chakra.json.test(1000) );

//支持以复杂的 JavaScript 表达式作为下标获取并调用 JavaScript 函数
console.dump( chakra.json["new ES6().test"](1000) );

/*
Chakra 性能更强悍，支持 ES6，但�?COM 接口的支持不�?JScript�?在使用上�?JScript 有很多区�?*/
console.pause();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/JScript/es6.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/JScript/es6.md')

