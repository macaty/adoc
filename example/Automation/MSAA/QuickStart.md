[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: MSAA 自动化入�?
```aardio aardio
//MSAA 自动化入�?//入门教程: https://mp.weixin.qq.com/s/qeQGC9rnOqaLZvZmHhroKw
//探测工具 loadcodex("~\tools\Spy\inspect.aardio")

import winex;
import winex.accObject;
import winex.key;

//遍历浏览器窗口（兼容 Chrome，Edge 等）
for hwnd,title in winex.each("Chrome_WidgetWin_1") {

    //获取 MSAA 接口对象
    var accObject = winex.accObject.fromWindow(hwnd);

    //查找文本�?    var edit = accObject.find(
        role = 0x2A;
        name = "<Address and search bar>|<地址和搜索栏>";
    )

    if(edit){
        //获取浏览器地址栏内�?        var url = edit.value();

        //修改浏览器地址栏内�?        edit.setValue("javascript:alert(document.location.href)")
        edit.takeFocus();

        //后台发送按键消�?        winex.key.click(hwnd,"ENTER");
        thread.delay(1000);
    }
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/MSAA/QuickStart.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/MSAA/QuickStart.md')

