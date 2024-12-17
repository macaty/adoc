[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 获取桌面图标信息

```aardio aardio
//获取桌面图标信息
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

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/winex.desktop.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/winex.desktop.md')

