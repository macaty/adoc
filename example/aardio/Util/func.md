[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 函数扩展

```aardio aardio
//函数扩展

import util;
import console;

//util.bind可用于修改函数的默认实参,并生成新的函�?string.findMail = util.bind( string.match, ,"\w+[\w\-\.]+\w@\w+[\w\-]*\w\.[\w\-\.]*\w{2,}" )
string.endWith = util.bind( string.endWith, , ,true)

console.log(
    string.findMail("aaaaaaaaaa web@aardio.com "),
    string.endWith( "a abc","ABC" )
)

//===================================================
var func = function(){
    console.log("a")
}

var proc = function(){
    console.log("b")
}

//在调用一个函数前触发钩子函数,钩子函数返回任意非空值可中止目标函数执行
var func = util.before(,func,proc);
func()

//===================================================
var tab = {
    name = "名字";
    func = function(){
        console.log( owner[["name"]] )
    }
}

var func = tab.func;
func() //调用失败

var func = util.hitch(tab,"func");
func() //owner对象不再受前缀影响

console.pause()

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Util/func.md)

