[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 修改文件权限

```aardio aardio
//修改文件权限
import fsys;
import process.popen;
import sys.acl;

var path = io.fullpath( "/cacls.aardio" )

//禁止所有文件权�?禁止删除
var prcs = process.popen("cacls.exe",path,"/P ",sys.acl.getUserName()+":n", "/C")
prcs.write('y\r\n');
prcs.close();

//恢复完全控制权限
/*
var prcs = process.popen("cacls.exe",path,"/P","everyone:F","/C ")
prcs.write('y\r\n');
prcs.close();
*/

//使用标准库提供的 fsys.acl 可以更简洁地执行上面的操作（可省略命令行参数）�?//import fsys.acl;
//fsys.acl.cacls("/cacls.aardio"," /P everyone:F /C ");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/Permissions/cacls.md)

