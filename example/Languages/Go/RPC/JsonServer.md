[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Go 璇█ - RPC 鏈嶅姟绔?
```aardio aardio
//aardio 璋冪敤 Go 璇█ -  RPC 鏈嶅姟绔?import golang;
var go = golang();//鍒涘缓 Go 缂栬瘧鍣紙 浠呬粎璋冪敤缂栬瘧鍚庣殑 EXE 涓嶉渶瑕?锛?
//Go 涓?aardio 涓�鏍凤紝婧愮爜涓庡瓧绗︿覆榛樿涓?UTF-8 缂栫爜
go.main = /**********
package main

import (
    "net/rpc"
    "aardio/jsonrpc" //婧愮爜锛?~\lib\golang\.res\aardio\jsonrpc\jsonrpc.go"
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

    //杩愯 RPC 鏈嶅姟绔?    jsonrpc.Run(server)
}
**********/

//涓婇潰鐨?go.main 浼氳嚜鍔ㄤ繚瀛樺埌鏂囦欢锛岀劧鍚庣紪璇?Go 婧愮爜鐢熸垚鍚屽悕 EXE 鏂囦欢
go.buildStrip("/goRpc.go");

//鍒ゆ柇鏄惁鍗曠嫭杩愯姝ょず渚?if(...) console.close();
else console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/JsonServer.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/RPC/JsonServer.md')

