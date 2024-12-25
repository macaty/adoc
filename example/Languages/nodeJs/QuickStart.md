[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Node.js - 设置 startEnviron

```aardio aardio
//aardio 调用 Node.js - 设置 startEnviron
import console;
import nodeJs;

/*
JavaScript 快速入门：
https://quickref.me/zh-CN/docs/javascript.html
https://learnxinyminutes.com/docs/zh-cn/javascript-cn/
*/

var js = /******

console.log(process.argv.slice(2));

var startEnviron = require('startEnviron');
console.log(startEnviron.dest);

******/

//自动分析 JS 代码中的 require 语句并安装依赖模�?nodeJs.requireByJs(js);

//把对象传�?node.js，在 JS 代码中用 require('startEnviron') 获取�?nodeJs.startEnviron({
    src:"传个字符�?,dest:{test:"嵌套的对象表，传给node.js都没问题",number:123, arr:{1,2,3} }
})

//执行JS，这里指定的启动参数�?JS 代码中可�?process.argv 获取�?var prcs = nodeJs.exec(js,"args1","args2");
prcs.logResponse();

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/QuickStart.md)

