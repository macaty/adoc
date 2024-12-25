[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - 进程启动参数

```aardio aardio
//aardio 调用 Go 语言 - 进程启动参数
import golang;
var go = golang();//创建 Go 编译器（ 仅仅调用编译后的 EXE 不需�?�?
//Go源码与字符串都是 UTF-8 编码，跟 aardio 一样很方便
go.main  = /****************
package main

import (
    "flag"
    "fmt"
    "encoding/json"
)

//结构体，字符后的字符�?tag 可用于辅�?JSON 转换�?type Args struct {
    Num int  `json:"num"`
    Url string  `json:"url"`
    H bool  `json:"h"`
}

//用于获取命令行参�?var args = Args{}

//�?main 函数前执�?func init() {
    flag.BoolVar(&args.H, "H", false, "帮助")
    flag.IntVar(&args.Num, "num", 0, "请输入数�?)
    flag.StringVar(&args.Url, "url", "https://www.aardio.com", "请输入网址")
}

func main() {
    flag.Parse() //解析命令行参�?
    if args.H {
        flag.Usage()
    } else {
        //结构体输出为 JSON
        var jsonParam, _ = json.Marshal(args)
        fmt.Println(string(jsonParam))
    }
}
****************/

//编译 Go 源码生成 EXE 文件
go.build("/.go/flag.go");

//-------------------------调用 Go 程序-----------------------

import console.int;
import process.popen;
import process.job.limitKill;

//打开 Go 进程返回管道对象，路径首字符为单个斜杆或反斜杆表示应用程序根目录�?var prcs,err = process.popen("/.go/flag.exe",{
    "--num":123;
    "--url":"https://example.com"
})

//加入作业对象。主进程退出时退�?Go 程序自动退出�?prcs.assignToJobObject(process.job.limitKill);

//读取 Go 程序输出�?JSON，JSON 后必须有换行�?var data = prcs.json();
console.dump(data);

/*
请参考：
范例 > 调用其他语言 > Go > RPC
范例 > 进程 > 管道
*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/flag.md)

