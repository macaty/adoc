[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - 创建对象

```aardio aardio
//COM 接口 - 创建对象
import com;
import console;

//参考文档： https://www.aardio.com/zh-cn/doc/library-guide/builtin/com/com.html
//创建 COM 对象，注�?COM 有关的函数通常首字母大�?var fs = com.CreateObject("Scripting.FileSystemObject");

//使用 COM 对象
var dir = fs.GetFolder( io.fullpath("/") );

//遍历COM对象成员
for index,file in com.each(dir.Files) {
    console.log(file.path);
}
console.more();

//查看 COM 对象成员
console.dump( com.DumpTypeInfo(dir) );

//上面的函数可以简写为
console.dump( dir );

//输出更详细的 COM 对象类型库信�?import com.tlbDoc;
com.tlbDoc.dump( dir );//�?com.tlbDoc(dir) 可以得到输出的文�?
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/GettingStarted/CreateObject.md)

