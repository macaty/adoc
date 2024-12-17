[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 杩唬鍣?
```aardio aardio
//COM 杩唬鍣?import com;
import console;

//鍒涘缓 COM 瀵硅薄
var shell = com.CreateObject("Shell.Application");

//璋冪敤 COM 瀵硅薄鍑芥暟锛岃繑鍥?COM 瀵硅薄
var dir = shell.NameSpace(io._exedir);

//閬嶅巻 COM 瀵硅薄闆嗗悎
for index,item in com.each( dir.Items ) {
    console.log(
        item.Name,
        item.Path,
        math.size64(item.Size).format()
    )
}
console.more(,true);

//鑾峰彇璧勬簮绠＄悊鍣ㄤ腑鎵�鏈夐�変腑鐨勬枃浠惰矾寰?import com.shell;
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Advanced/com.each.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Advanced/com.each.md')

