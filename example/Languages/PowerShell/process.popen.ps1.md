[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 运行 ps1 文件

```aardio aardio
//aardio 运行 ps1 文件
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
var ps1  = process.popen.ps1("/test.ps1");//不需要设置权�?/*
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/PowerShell/process.popen.ps1.md)

