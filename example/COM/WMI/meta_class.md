[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 搜索 WMI 类名

```aardio aardio
//搜索 WMI 类名
import console;
import com.wmi;

var wmi = com.wmi("\root\cimv2")

//WMI 的查询语法为 WQL (SQL for WMI)
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/WMI/meta_class.md)

