[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 yaegi 脚本 - 回调函数

```aardio aardio
//aardio 调用 Go 语言 yaegi 脚本 - 回调函数
import golang.yaegi;
var go = golang.yaegi();

go.eval(`
package main

//导入模块
import (
    "aardio"
)

func TestCallBack(fnCallback float64) int{

    var s = "字符�?

    /*
    回调 aardio �?raw.jsonCall 创建的函数指针�?    支持可变参数（使�?JSON 自动转换参数），aardio 函数返回 null �?int 类型整数�?�?    aardio.CallJson() 返回类型�?(int,error)�?
    注意：aardio �?Go 导出函数所在的默认 goroutine 之间的互调属于同一线程（这里不用考虑多线程）�?    */
    var r,_ = aardio.CallJson( fnCallback ,s,123,map[string]int{"id": 1, "id2": 2} )

    return r
}

`)

import raw.jsonCall

//创建回调函数指针�?�?Go 中必须用 aardio.CallJson 调用�?var callback = raw.jsonCall(
    function(a,b,c){
        console.log("回调参数:",a,b)
        console.dumpJson(c);
        return 123;
    } );

import console.int

/*
golang.yaegi 会将函数指针转换为数值�?而所有数值参数的类型都是 float64，所�?Go 参数要声明类型为 float64�?其他类型可自 float64 转换过去�?*/
var ret  = go.TestCallBack( callback )

console.log(ret);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/Yaegi/jsonCall.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/Yaegi/jsonCall.md')

