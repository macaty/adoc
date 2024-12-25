[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Go 语言 - 安装模块

```aardio aardio
//aardio 调用 Go 语言 - 安装模块
import golang;

//参数 @1 指定工作目录，默认为 "/"
var go = golang("/go")

//可选设置代�?//go.setHttpProxy("http://127.0.0.1:1082");
//go.setGoProxy("https://mirrors.aliyun.com/goproxy/,direct");

//初始化项�?go.mod("init golang/mdns")

//下载第三方模�?go.get("github.com/miekg/dns")
go.get("github.com/hashicorp/mdns")

//下面�?golang.mdns 的部分源码，完整源码请查看该扩展�?go.main = /**********
package main

import "C"
import (
    "github.com/hashicorp/mdns"
    "net"
    "encoding/json"
)

type NewServiceParam struct {
    Instance string `json:"instance"`
    Service  string `json:"service"`
    Domain   string `json:"domain"`
    Host     string `json:"host"`
    Ips []   string `json:"ips"`
    Txt []   string `json:"Txt"`
    Port     int    `json:"port"`
}

var server *mdns.Server;

//export StartService
func StartService(serviceParamPtr *C.char)  {

    newServiceParam := NewServiceParam{}
    json.Unmarshal( []byte(C.GoString( serviceParamPtr )), &newServiceParam)

    var ips []net.IP
    size := len(newServiceParam.Ips)
    for i := 0; i < size; i++ {
        ip :=  net.ParseIP(newServiceParam.Ips[i]);
        if(ip != nil){
            ips = append(ips,ip);
        }
    }

    var service *mdns.MDNSService
    service, _ = mdns.NewMDNSService(newServiceParam.Instance,newServiceParam.Service,newServiceParam.Domain, newServiceParam.Host,newServiceParam.Port,ips,newServiceParam.Txt)

    server, _ = mdns.NewServer(&mdns.Config{Zone: service})
}

func main(){}
**********/
go.buildShared("/mdns.go");

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Go/Module/mod.md)

