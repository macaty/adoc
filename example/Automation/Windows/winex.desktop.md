[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鑾峰彇妗岄潰鍥炬爣淇℃伅

```aardio aardio
//鑾峰彇妗岄潰鍥炬爣淇℃伅
import winex.desktop;
import console;

var count = winex.desktop.listview.count;
var rcItem = ::RECT();

for(i=1;count ) {

    var itemText = winex.desktop.listview.getItemText(i);
    winex.desktop.listview.getItemRect(i,,rcItem);

    console.log( itemText,'\t', rcItem.left,rcItem.top )
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/winex.desktop.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/winex.desktop.md')

