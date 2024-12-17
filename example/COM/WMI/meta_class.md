[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎼滅储 WMI 绫诲悕

```aardio aardio
//鎼滅储 WMI 绫诲悕
import console;
import com.wmi;

var wmi = com.wmi("\root\cimv2")

//WMI 鐨勬煡璇㈣娉曚负 WQL (SQL for WMI)
//https://docs.microsoft.com/en-us/windows/win32/wmisdk/like-operator
var classes = wmi.ExecQuery("SELECT * FROM meta_class WHERE __class LIKE 'Win32_%'")

var qualName = { "dynamic","static" }

for i,cls in com.each(classes) {

  if(!cls.Methods_.Count){ continue; }

  for i,q  in ..com.each(cls.Qualifiers_) {
    if( !qualName || ..table.find(qualName,..string.lower(q.Name) ) ){
        console.log(cls.Path_.Class)
    }
  }
}

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/WMI/meta_class.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/WMI/meta_class.md')

