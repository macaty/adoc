[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# builtin.struct 库模块帮助文�?
## pointObject 成员列表

::POINT 结构体对象，包含用于表示坐标的数值字�?x,y

### pointObject.x

x坐标

### pointObject.y

y坐标

## rectObject 成员列表

::RECT 结构体对象，包含用于表示区块位置的数值字�?left,top,right,bottom

### rectObject.bottom

�?
### rectObject.contains(x,y)

检测指定的 x,y 坐标是否位于矩形区块�?
### rectObject.copy

复制并返回新的矩形区块结构体

### rectObject.copy()

[返回对象:rectObject](../global/_.html#rectObject)

### rectObject.copy(width,height)

可选在参数中指定新的宽度、高�?
所有参数都可以省略

### rectObject.expand

扩展或缩小右下角坐标

### rectObject.expand()

[返回对象:rectObject](../global/_.html#rectObject)

### rectObject.expand(dx,dy)

dx指定正数扩展右边,负数缩小右边,

dy指定正数扩展底边,负数缩小底边

左上角不�?

返回自身

### rectObject.float()

无参数时转换�?::RECTF 结构体并返回该结构体

如果参数中指�?:RECTF结构�?则使用参数更新位区块自身,

指定参数则此函数无返回�?
[返回对象:rectfObject](../gdip/core.html#rectfObject)

### rectObject.height()

高度

### rectObject.inflate

扩大区块并返回矩形区块自�?
### rectObject.inflate()

[返回对象:rectObject](../global/_.html#rectObject)

### rectObject.inflate(左右单位,上下单位)

扩大区块并返回矩形区块自�?
忽略参数请传�?,不可省略

�?�?�?右分别扩大指定的单位

负数为缩�?
### rectObject.intersect

检测与参数指定的矩形区块相�?
### rectObject.intersect(rc)

检测与参数指定的矩形区块相�?
成功修改当前区块并返回自�?失败返回�?
### rectObject.intersectsWith

检测两个矩形区块是否碰撞相�?
### rectObject.intersectsWith(rc)

检测两个矩形区块是否碰撞相�?
### rectObject.left

�?
### rectObject.ltrb

用于�?x,y,width,height 转换�?left,top,right.bottom 并返�?
### rectObject.ltrb()

返回结构体的 left,top,right,bottom �?个�?
### rectObject.ltrb(x,y,width,height)

使用传入参数修改左、上坐标,以及宽度、高�?

返回结构体的left,top,right,bottom�?个�?
### rectObject.move

移动左上角坐�?
### rectObject.move()

[返回对象:rectObject](../global/_.html#rectObject)

### rectObject.move(dx,dy)

使用参数指定的x,y坐标偏移量移动左上角坐标,

正数向右下移�?负数向左上移�?

右下角位置不�?
返回自身

如果需要移动坐标且大小不变请改用offset函数

移动到指定坐标而不是偏移量请改用setPos函数

### rectObject.offset

移动矩形框并返回自身

### rectObject.offset()

[返回对象:rectObject](../global/_.html#rectObject)

### rectObject.offset(横偏�?纵偏�?

移动矩形框并返回自身,矩形大小不变,

左上移使用负坐标,右下移使用正坐标

忽略参数请传�?,不可省略

### rectObject.right

�?
### rectObject.setPos

重新调整坐标与大�?

返回结构体自�?
### rectObject.setPos()

[返回对象:rectObject](../global/_.html#rectObject)

### rectObject.setPos(x,y,cx,cy)

移动到x,y指定的坐�?

可选用cx,cy重新指定宽度和高�?

所有参数可�?不指定则保持旧�?
### rectObject.top

�?
### rectObject.width()

宽度

### rectObject.xywh

用于将left,top,right.bottom转换�?x,y,width,height 并返�?
### rectObject.xywh()

返回结构体的左上角坐标x,y 以及宽度width,高度height�?个�?
### rectObject.xywh(left,top,right,bottom)

修改左、上、右、下的�?

返回结构体的左上角坐标x,y 以及宽度width,高度height�?个�?
## sizeObject 成员列表

::SIZE 结构体对象，包含用于表示大小的数值字�?cx,cy

### sizeObject.cx

�?
### sizeObject.cy

�?
### 全局常量

### ::OffsetRect(rc,dx,dy)

移动矩形框，

此函数已废弃，请直接调用 rc.offset 函数

### ::POINT

整型坐标结构�?
此结构体通过标准�?builtin.struct 默认加载

### ::POINT()

[返回对象:pointObject](#pointObject)

### ::POINT(x,y)

创建整型坐标结构�?
可选在参数中指�?x,y 坐标初始�?
### ::RECT

表示矩形区块的结构体

此结构体通过标准�?builtin.struct 默认加载

### ::RECT()

[返回对象:rectObject](../global/_.html#rectObject)

### ::RECT(left,top,right,bottom)

创建矩形区块结构�?
可选在参数中指定左,�?�?下初始�?
### ::SIZE

整型尺寸结构�?
此结构体通过标准�?builtin.struct 默认加载

### ::SIZE()

[返回对象:sizeObject](#sizeObject)

### ::SIZE(cx,cy)

创建整型尺寸结构�?
可选在参数中指定宽�?cx,cy 初始�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/builtin/struct.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/builtin/struct.md')

