[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Go 璇█ - 瀹夎妯″潡

```aardio aardio
//aardio 璋冪敤 Go 璇█ - 瀹夎妯″潡
import golang;

//鍙傛暟 @1 鎸囧畾宸ヤ綔鐩綍锛岄粯璁や负 "/"
var go = golang("/go")

//鍙�夎缃唬鐞?//go.setHttpProxy("http://127.0.0.1:1082");
//go.setGoProxy("https://mirrors.aliyun.com/goproxy/,direct");

//鍒濆鍖栭」鐩?go.mod("init golang/mdns")

//涓嬭浇绗笁鏂规ā鍧?go.get("github.com/miekg/dns")
go.get("github.com/hashicorp/mdns")

//涓嬮潰鏄?golang.mdns 鐨勯儴鍒嗘簮鐮侊紝瀹屾暣婧愮爜璇锋煡鐪嬭鎵╁睍搴?go.main = /**********
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/Module/mod.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/Module/mod.md')

