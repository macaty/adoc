[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Node.js 函数

```aardio aardio
//aardio 调用 Node.js 函数
import console.int;
import nodeJs;

//JS 代码
var js = /******

global.Calculator = class  {
    static add(a, b) {
        return a + b;
    }

    static multiply(a, b) {
        return a * b;
    }
}

global.add = function (a, b) {
    return a + b;
}
******/

//启动 Node.js �?var node = nodeJs.startRpc(js,//指定 JS 代码或文件路径，这种方式�?JS �?console.log 不可�?    "args1","args2");//可选指定任意个启动参数( JS �?process.argv 获取 )�?
/*
调用 JS 函数，要点：
- 被调用的 JS 对象必须是全局对象 global 的成员对�?
- 被调用的函数应当是同步函数，不能是异步函数�?*/
var ret,err = node.Calculator.add(2,3);

//调用 JS 全局函数�?var ret,err = node.add(2,3);

//获取返回�?ret = ret[["result"]];

console.log(ret);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/nodeJs/startRpc.md)

