[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - 结构体操�?
```aardio aardio
//aardio 调用 Go 语言 - 结构体操�?import console.int;
import golang;
var go = golang();

go.main = /**********
package main

import "C"
import "unsafe"
import "fmt"

//声明结构�?type Point struct {
  x    int
  y    int
}

//export SetPoint
func SetPoint(p uintptr) {

    // aardio 结构体转换为 Go 结构�?    point := (*Point)(unsafe.Pointer(p))
    point.x = 1
    point.y = 2

    /*
    Go �?fmt.Println 打印变量很方便，可传入多个任意类型的参数�?    */
    fmt.Println( "�?Go 中打印结构体�?,point );
}

func main() {}
**********/

go.buildShared("/.go/TestStruct.go");

//------------------下面调用 DLL-----------------------

var goDll = raw.loadDll("/.go/TestStruct.dll",,"cdecl");

//声明结构�?class Point {
    int x;
    int y;
}

//创建结构�?var point = Point();

//调用 Go 函数，传结构体（结构体总是传址�?goDll.SetPoint(point);

//打印结构�?console.dumpJson(point);

//结构体就是表（table），也可以这样直接写
goDll.SetPoint({
    int x = 1;
    int y = 2;
});

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/struct.md)

