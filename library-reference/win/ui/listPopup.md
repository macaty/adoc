[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.listPopup 库模块帮助文�?
## win.ui 成员列表

### win.ui.listPopup

弹出列表�?
### win.ui.listPopup()

创建弹出列表�?
参数中指定edit,或richedit控件对象

[返回对象:winuilistpopupObject](#winuilistpopupObject)

## winuilistpopupObject 成员列表

### winuilistpopupObject.height

显示高度

### winuilistpopupObject.onComplete

```aardio aardio
winuilistpopupObject.onComplete = function(text){
    /*用户已完成输�?在候选列表中选中某项并已完成输入
或者在输入后直接回车可触发此事�?/;
}

```

### winuilistpopupObject.onGetItems

```aardio aardio
winuilistpopupObject.onGetItems = function(text){
    return {/*text参数是用户已输入的文�?返回要显示的字符串数�?
可选在�?个返回值返回要选中的索�?/};
}

```

### winuilistpopupObject.onSetText

```aardio aardio
winuilistpopupObject.onSetText = function(text){
    /*用户已选择列表�?text参数为列表项选中的文�?返回值为确认输入的文�?/;
    return text;
}

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/listPopup.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/listPopup.md')

