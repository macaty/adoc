[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 入门

```aardio aardio
//窗口程序 - 入门
//请按 F5 运行查看教程

/*
窗口程序入门指南�?https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/basic.html

创建窗口与控件入门教程：
https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/create-winform.html
*/

var fb = fiber.create(
    function(){
        import win.ui;
        mainForm = win.form(text="窗口程序入门";right=959;bottom=591)

        mainForm.add(
        custom={cls="\dlg\main\userInfo.aardio";text="custom";left=568;top=944;right=944;bottom=584;db=1;dr=1;z=1};
        tab={cls="tab";left=8;top=16;right=944;bottom=536;db=1;dl=1;dr=1;dt=1;edge=1;z=2}
        )

        mainForm.tab.loadForm("\dlg\main\tabs1.aardio");
        mainForm.tab.loadForm("\dlg\main\tabs2.aardio");
        mainForm.tab.loadForm("\dlg\main\tabs3.aardio");

        mainForm.show();
        win.loopMessage();

    },"~\extensions\wizard\project2\template\winform\"
)

fiber.resume(fb)

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/QuickStart.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/QuickStart.md')
