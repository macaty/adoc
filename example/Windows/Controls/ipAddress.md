[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: IP地址控件演示

```aardio aardio
//IP地址控件
import win.ui;
/*DSG{{*/
var winform = win.form(text="IP地址控件演示";right=599;bottom=399)
winform.add(
ipAddress={cls="ipaddress";text="IP 地址";left=152;top=84;right=408;bottom=105;bgcolor=16777215;edge=1;z=1}
)
/*}}*/

winform.ipAddress.setRange("10.1.0.0","10.10.255.255");
winform.ipAddress.address = 10 << 24 | 1 << 16;

winform.ipAddress.onFieldChanged = function(field,value){
    winform.text = winform.ipAddress.text + " 变更位置:" + field + " 数�?" + value;
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/ipAddress.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/ipAddress.md')

