[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.util.paint 库模块帮助文�?
## win.util 成员列表

### win.util.paint

简单画�?
### win.util.paint()

创建简单画�?参数必须指定一个plus控件

plus控件的背景色建议设置为白�?
[返回对象:winutilpaintObject](#winutilpaintObject)

## winutilpaintObject 成员列表

### winutilpaintObject.drawColor

画笔颜色,使用橡皮擦时必须改为背景�?
### winutilpaintObject.drawMode

设置绘画工具

### winutilpaintObject.drawWidth

画笔宽度

### winutilpaintObject.onEndDrawing

```aardio aardio
winutilpaintObject.onEndDrawing = function(){
    /*开始画图触�?/
}

```

### winutilpaintObject.onStartDrawing

```aardio aardio
winutilpaintObject.onStartDrawing = function(){
    /*开始画图触�?/
}

```

### winutilpaintObject.undo()

撤消

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/util/paint.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/util/paint.md')

