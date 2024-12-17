[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - 生成 COM 接口 DLL

```aardio aardio
//aardio 调用 Go 语言 - 生成 COM 接口 DLL
import console.int;
import golang;

//参数 @1 指定工作目录，默认为 "/"
var go = golang("/go")
go.setGoProxy("https://mirrors.aliyun.com/goproxy/,direct");

//初始化项�?go.mod("init golang/dispDemo")

//下载第三方模�?go.get("github.com/go-ole/go-ole")

go.main = /**********
package main

import (
    "C"
    "unsafe"
    "github.com/go-ole/go-ole"
    "github.com/go-ole/go-ole/oleutil"
    "fmt"
)

//export TestDispatch
func TestDispatch(dispatchIn uintptr) uintptr {
    //这里不需要初始化 OLE，aardio 自动支持这些

    // 获取传入�?IDispatch 指针
    dispatch := (*ole.IDispatch)(unsafe.Pointer(dispatchIn))

    // 调用 dispatch 对象的方�?    result := oleutil.MustCallMethod(dispatch, "Add", 1, 2)
    defer result.Clear()

    // 假设 Add 方法返回一个数值，可以这样获取返回�?    // value := result.Value() // 返回 interface{}
    // valueInt := result.ToInt() // 返回 int
    // valueFloat := result.ToFloat() // 返回 float64
    // valueString := result.ToString() // 返回 string

    // 打印结果（假设返回一个数值）
    fmt.Println("Result:", result.Value())

    // 创建新的 IDispatch 对象
    clsid, err := ole.CLSIDFromProgID("Scripting.Dictionary")
    if err != nil {
        panic(err)
    }

    unknown, err := ole.CreateInstance(clsid, nil)
    if err != nil {
        panic(err)
    }
    defer unknown.Release()

    //这里增加引用计数
    newDispatch, err := unknown.QueryInterface(ole.IID_IDispatch)
    if err != nil {
        panic(err)
    }

    // 返回新的 IDispatch 对象的指针（不必释放引用计数，由 aardio 接收时释放）
    return uintptr(unsafe.Pointer(newDispatch))
}

func main() {
    // 需要有一个空�?main 函数以满�?go build
}
**********/
go.buildShared("/dispDemo.go");

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/COM Interface/disp-dll.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/COM Interface/disp-dll.md')

