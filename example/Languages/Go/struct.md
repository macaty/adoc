[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Go 璇█ - 缁撴瀯浣撴搷浣?
```aardio aardio
//aardio 璋冪敤 Go 璇█ - 缁撴瀯浣撴搷浣?import console.int;
import golang;
var go = golang();

go.main = /**********
package main

import "C"
import "unsafe"
import "fmt"

//澹版槑缁撴瀯浣?type Point struct {
  x    int
  y    int
}

//export SetPoint
func SetPoint(p uintptr) {

    // aardio 缁撴瀯浣撹浆鎹负 Go 缁撴瀯浣?    point := (*Point)(unsafe.Pointer(p))
    point.x = 1
    point.y = 2

    /*
    Go 鐢?fmt.Println 鎵撳嵃鍙橀噺寰堟柟渚匡紝鍙紶鍏ュ涓换鎰忕被鍨嬬殑鍙傛暟銆?    */
    fmt.Println( "鍦?Go 涓墦鍗扮粨鏋勪綋锛?,point );
}

func main() {}
**********/

go.buildShared("/.go/TestStruct.go");

//------------------涓嬮潰璋冪敤 DLL-----------------------

var goDll = raw.loadDll("/.go/TestStruct.dll",,"cdecl");

//澹版槑缁撴瀯浣?class Point {
    int x;
    int y;
}

//鍒涘缓缁撴瀯浣?var point = Point();

//璋冪敤 Go 鍑芥暟锛屼紶缁撴瀯浣擄紙缁撴瀯浣撴�绘槸浼犲潃锛?goDll.SetPoint(point);

//鎵撳嵃缁撴瀯浣?console.dumpJson(point);

//缁撴瀯浣撳氨鏄〃锛坱able锛夛紝涔熷彲浠ヨ繖鏍风洿鎺ュ啓
goDll.SetPoint({
    int x = 1;
    int y = 2;
});

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/struct.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/struct.md')

