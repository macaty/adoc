[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# gdip.region 库模块帮助文�?
## gdip 成员列表

### gdip.region

GDI+ Region 对象

### gdip.region()

创建一个无限区�?
[返回对象:GdipRegionObject](#GdipRegionObject)

### gdip.region(HRGN)

�?GDI 区域句柄创建

### gdip.region(region)

�?gdip.region 区域对象复制一个对�?
### gdip.region({left=,top=,right=,bottom=})

�?::RECT 矩形创建区域�?
传入普通表会自动转换为 ::RECT 结构体，只要指定 ::RECT 的所有字段值就可以

### gdip.region({x=,y=,width=,height=})

�?::RECTF 矩形创建区域�?
传入普通表会自动转换为 ::RECT 结构体，只要指定::RECT 的所有字段值就可以

## GdipRegionObject 成员列表

### GdipRegionObject.combine(param,mode)

与指定区域、路径或矩形相交�?
参数 @param 可以�?gdip.region 对象、gdip.path 对象 �?:RECT �?:RECTF 结构体�?
指定对应结构体字段值的普�?table 会自动转换为 ::RECT �?::RECTF 结构体�?
参数 @mode 指定 \_gdipCombine 前缀的常量�?
### GdipRegionObject.delete()

删除对象，对象回收时也会自动调用此对象�?
可重复调用，但删除对象以后不能再调用对象的其他函数�?
### GdipRegionObject.exclude()

排除指定区域、路径或矩形�?
参数 @1 可以�?gdip.region 对象、gdip.path 对象 �?:RECT �?:RECTF 结构体�?
指定对应结构体字段值的普�?table 会自动转换为 ::RECT �?::RECTF 结构�?
### GdipRegionObject.getData()

返回区域数据，返回值为 buffer 类型字节数组�?
### GdipRegionObject.intersect()

与指定区域、路径或矩形相交�?
参数 @1 可以�?gdip.region 对象、gdip.path 对象 �?:RECT �?:RECTF 结构体�?
指定对应结构体字段值的普�?table 会自动转换为 ::RECT �?::RECTF 结构�?
### GdipRegionObject.isEmpty()

是否为空区域，参�?@1 指定 gdip.graphics 对象�?
### GdipRegionObject.isInfinite()

是否为无限区域，参数 @1 指定 gdip.graphics 对象�?
### GdipRegionObject.makeEmpty()

将区域设为空

### GdipRegionObject.makeInfinite()

将区域设为无�?
### GdipRegionObject.translate(dx,dy)

平移区域，参�?dx,dy 指定水平与垂直方向平移数�?
## gdip.path 成员列表

### gdip.path.is()

参数 @1 是否 gdip.region 对象

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/gdip/region.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/gdip/region.md')

