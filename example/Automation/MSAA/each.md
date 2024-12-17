[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: MSAA 鑷姩鍖?- 閬嶅巻鍏冪礌

```aardio aardio
//MSAA 鑷姩鍖?- 閬嶅巻鍏冪礌
import winex;
import winex.accObject;
import console;

for hwnd in winex.each( "TXGuiFoundation" ) {
    var accObject = winex.accObject.fromWindow(hwnd)
    if(accObject){
        var accMessage = accObject.find(role="list")
        if(accMessage){
            for accChild in accMessage.each(){
                console.log(accChild.roleText(),accChild.name(),accChild.value())
            }
        }

        var accEditor = accObject.find(
            role = "editable text";
            name = "杈撳叆";
        )

        if(accEditor){
            var r = accEditor.takeFocus();
            winex.sayIme("test",hwnd)
        }
    }
}

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/MSAA/each.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/MSAA/each.md')

