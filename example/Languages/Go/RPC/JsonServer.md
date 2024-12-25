[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - RPC 服务�?
```aardio aardio
//aardio 调用 Go 语言 -  RPC 服务�?import golang;
var go = golang();//创建 Go 编译器（ 仅仅调用编译后的 EXE 不需�?�?
//Go �?aardio 一样，源码与字符串默认�?UTF-8 编码
go.main = /**********
package main

import (
    "net/rpc"
    "aardio/jsonrpc" //源码�?~\lib\golang\.res\aardio\jsonrpc\jsonrpc.go"
)

type Calculator struct{}

type Args struct {
    X, Y int
}

func (t *Calculator) Add(args *Args, reply *int) error {
    *reply = args.X + args.Y
    return nil
}

func main() {
    server := rpc.NewServer()
    server.Register( new(Calculator) )

    //运行 RPC 服务�?    jsonrpc.Run(server)
}
**********/

//上面�?go.main 会自动保存到文件，然后编�?Go 源码生成同名 EXE 文件
go.buildStrip("/goRpc.go");

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/JsonServer.md)

