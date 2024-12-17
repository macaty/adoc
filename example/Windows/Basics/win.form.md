[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 创建 winform 窗口的隐藏参�?
```aardio aardio
//创建 winform 窗口的隐藏参�?//为避免滥用而在窗体设计器中隐藏的部分参数说�?//入门教程: https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/create-winform.html

import win.ui;

/*
在窗体设计器中自动生成的代码如下�?一般我们不建议手动修改设计器生成的代码�?但是aardio仍然预留了一些必须手动修改的隐藏参数�?例如 className,style,styleEx等等�?*/
var winform = win.form(
    /*
    如果指定了cls，则在cls后面追加线程ID生成窗口类名�?    如果同时指定了className，则className必须指向一个已存在的窗口类�?    aardio自该窗口类复制一个副本�?
    如果指定了className，但是并没有指定cls，则className指定真实类名�?    如果此窗口类不存在会自动创建.

    如果cls,className都不指定,则生成默认类�?    */
    className="aardio_form_class_name";

    /*
    可以使用style指定样式,所有控件也都可以在创建参数中指定默�?style 参数
    */
    style=0x2000000/*_WS_CLIPCHILDREN*/;

    /*
    可以使用exstyle指定扩展样式,所有控件也都可以在创建参数中指默认  exstyle参数
    */
    exstyle = 0x20/*_WS_EX_TRANSPARENT*/;

    text="创建窗口的隐藏参�?;
    right=759;
    bottom=469
)
winform.add(
    edit={
        /*
        允许通过 id 参数自定义控�?ID�?        如果不指�?id，则自动分配 ID,自动分配 ID 时自 _IDCANCEL+1 开始逐渐递增�?        */
        id = 123;
        cls="edit";text="edit";left=46;top=29;right=722;bottom=435;edge=1;multiline=1;z=1;
        style=0x4000000/*_WS_CLIPSIBLINGS*/;

        //所有控件默认自适应窗口缩放 —�?自动调整窗口位置和大小�?        //如果在创建控件属性中指定 autoResize=false 则关闭自适应调整的功�?        autoResize=false
    }
)

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/win.form.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/win.form.md')

