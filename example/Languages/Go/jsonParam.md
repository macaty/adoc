[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - JSON 自动同步

```aardio aardio
//aardio 调用 Go 语言 - JSON 自动同步
import golang;
var go = golang();

go.main = /**********
package main

import "C"
import (
    "time"
    "aardio"
)

/*
Go 结构�?JSON 字段要大写首字母�?每个字段可以在类型名后面额外添加 tag 字符串声明在 JSON 中的字段名�?*/
type QueryParam struct {
    Service             string           `json:"service"`
    Domain              string           `json:"domain"`
    Timeout             time.Duration    `json:"timeout"`
}

//export Query
func Query(json *string) {

    //创建结构�?    var queryParam = QueryParam{}

    /*
    解析 JSON 到结构体�?    aardio.JsonParam() 返回函数对象用于更新 JSON�?    defer 语句用于推迟到函数退出前调用�?    */
    defer aardio.JsonParam(json, &queryParam)()

    //读取结构体的值，修改结构体的值，aardio 可以自动获取新�?    queryParam.Domain = queryParam.Domain + "|www.aardio.com"
}

func main(){}
**********/

go.buildShared("/.go/jsonTest.go");
var dll = raw.loadDll("/.go/jsonTest.dll",,"cdecl");

import golang.string;

//参数不是字符串、buffer、null 时会自动转换�?JSON 字符�?var jsonParam = golang.string({
    service = "_services._dns-sd._udp";
    domain = "local";
    timeout = 1000;
})

//调用 Go 函数
dll.Query( jsonParam );

/*
只要存储的是自动转换�?JSON 的对象，
那么 Go 修改 JSON �?aardio 也会自动解析 JSON 为对象�?
通过 value 获取解析后的对象�?*/
var goObject = jsonParam.value;

//查看对象的字段值，已经�?Go 修改�?console.dumpJson( goObject.domain )

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/jsonParam.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/jsonParam.md')

