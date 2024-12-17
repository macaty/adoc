[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 杩愯 ps1 鏂囦欢

```aardio aardio
//aardio 杩愯 ps1 鏂囦欢
import console;
console.open();

string.save("/test.ps1",`
if ($PSVersionTable.PSVersion.Major -lt 3){
    Add-Type -assembly system.web.extensions
    function ConvertTo-Json([object] $item){
        $jss=New-Object system.web.script.serialization.javascriptSerializer
        return $jss.Serialize($item)
    }
};

function Get-Version {
    ConvertTo-Json( $PSVersionTable.PSVersion )
}

Get-Version
`)

import process.popen;
var ps1  = process.popen.ps1("/test.ps1");//涓嶉渶瑕佽缃潈闄?/*
for( all,out,err in ps1.each() ){
    console.writeText(out,err );
}
*/

var json = ps1.readAll();

import web.json;
var psVersion = web.json.parse(json);
console.dump(psVersion);

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/process.popen.ps1.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/process.popen.ps1.md')

