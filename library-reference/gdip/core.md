[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.core 库模块帮助文�?
## gdip 成员列表

### gdip.POINTF

浮点格式坐标

### gdip.POINTF()

[返回对象:pointObject](#pointObject)

### gdip.POINTF(x,y)

浮点格式坐标

### gdip.RECTF()

[返回对象:rectfObject](core.html#rectfObject)

### gdip.RECTF(x,y,width,height)

浮点格式区块

### gdip.assert(/\*请输入GDI+函数返回值\*/)

校验GDI+函数返回�?
如果返回值非�?则抛出错误信�?
否则返回该函数的所有输出参�?
### gdip.assert2(/\*请输入GDI+函数返回值\*/)

校验GDI+函数返回�?
如果返回值非�?则向上层调用函数抛出错误信息

否则返回该函数的所有输出参�?
### gdip.checkError(/\*请输入GDI+函数返回值\*/)

如果有错误调用error函数抛出异常

### gdip.checkError(/\*请输入GDI+函数返回值\*/,2)

如果有错误调用error函数抛出异常

参数2指定抛出异常的调用级�?
2表示调用当前函数的函�?
### gdip.close()

关闭GDI+

在程序退出时会自动调用此函数

一般不需要显示调用此函数

### gdip.errMsg\[\]

根据返回值取错误信息

### gdip.open()

初始化GDI+

导入gdip时会默认执行此函�?
## rectfObject 成员列表

### rectfObject.height

�?
### rectfObject.ltrb

用于�?x,y,width,height 转换�?left,top,right.bottom 并返�?
### rectfObject.ltrb()

转换结构体的位置大小并返回为 left,top,right,bottom �?4 个�?
### rectfObject.ltrb(x,y,width,height)

使用传入参数修改左、上坐标,以及宽度、高度，

转换并返�?left,top,right,bottom �?4 个�?
### rectfObject.width

�?
### rectfObject.x

x坐标

### rectfObject.xywh

用于 将left,top,right.bottom 转换�?x,y,width,height 并返�?
### rectfObject.xywh()

返回结构体的左上角坐�?x,y 以及宽度 width,高度 height �?个�?
### rectfObject.xywh(left,top,right,bottom)

使用参数指定的左、上、右、下位置修改结构体存储的位置�?
返回结构体的左上角坐�?x,y 以及宽度 width,高度 height �?个�?
### rectfObject.y

y坐标

### 全局常量

### ::Gdiplus

[返回对象:dllModuleObject](../raw/_.html#dllModuleObject)

### ::POINTF

浮点格式坐标

### ::POINTF()

[返回对象:pointObject](#pointObject)

### ::POINTF(x,y)

浮点格式坐标

### ::RECTF

浮点格式区块

### ::RECTF()

[返回对象:rectfObject](core.html#rectfObject)

### ::RECTF(x,y,width,height)

浮点格式区块

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/core.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/core.md')

