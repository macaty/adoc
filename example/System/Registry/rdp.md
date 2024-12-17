[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 注册表操�?- 清除远程桌面连接记录

```aardio aardio
//注册表操�?- 清除远程桌面连接记录
import win.reg;

var reg = win.reg("HKEY_CURRENT_USER\SOFTWARE\Microsoft\Terminal Server Client\Default")
for(name,value,t in reg.eachValue()) {
    if(string.startWith(name,"MRU")){
        reg.delValue(name)
    }
}

var reg = win.reg("HKEY_CURRENT_USER\SOFTWARE\Microsoft\Terminal Server Client\Servers")
for(keyName,writeTime in reg.eachKey() ){
    reg.delKey(keyName)
}

io.remove(io.getSpecial(0x5/*_CSIDL_MYDOCUMENTS*/,"Default.rdp"))

import win.dlg.message;
win.dlg.message().ok("已清除远程桌面连接记�?)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Registry/rdp.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Registry/rdp.md')

