[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 迭代�?
```aardio aardio
//COM 迭代�?import com;
import console;

//创建 COM 对象
var shell = com.CreateObject("Shell.Application");

//调用 COM 对象函数，返�?COM 对象
var dir = shell.NameSpace(io._exedir);

//遍历 COM 对象集合
for index,item in com.each( dir.Items ) {
    console.log(
        item.Name,
        item.Path,
        math.size64(item.Size).format()
    )
}
console.more(,true);

//获取资源管理器中所有选中的文件路�?import com.shell;
for i,shWnd in com.shell.eachWindow(){
    var typeName = com.GetTypeInfo(shWnd.document).GetDocumentation().name;
    if(typeName=="IShellFolderViewDual3" || typeName=="IShellFolderViewDual2"){
        var items = shWnd.document.SelectedItems();
        for index,item in com.each(items) {
            console.log(item.Path,shWnd.HWND);
        }
    }
}

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/Advanced/com.each.md)

