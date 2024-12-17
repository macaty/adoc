[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: MSAA 自动�?- 遍历元素

```aardio aardio
//MSAA 自动�?- 遍历元素
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
            name = "输入";
        )

        if(accEditor){
            var r = accEditor.takeFocus();
            winex.sayIme("test",hwnd)
        }
    }
}

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/MSAA/each.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/MSAA/each.md')

