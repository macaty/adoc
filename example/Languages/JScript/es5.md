[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: ES5

```aardio aardio
//ES5
import console;
import web.script.es5;

var js = web.script();

js.script = /*****
var result = 0;
var numbers = [1,2,3];

if(Array.isArray(numbers)){
    numbers.forEach(function(value) {
    result = result + value;
    });
}

*****/

console.dump( js.script.result );
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/JScript/es5.md)

