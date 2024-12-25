[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.imageList 库模块帮助文�?
## win 成员列表

### win.imageList()

[返回对象:imageListObject](#imageListObject)

### win.imageList(句柄)

通过句柄创建一�?imageList

### win.imageList(宽度,高度)

创建一�?imageList

## win.imageList 成员列表

图像列表�?
可用于工具条、树形控件等�?
图像列表默认并不会自适应 DPI 缩放（控件已实现缩放的除外）�?
可在窗口或控件的 onDpiChanged 事件内更换不同大小的图像列表�?
建议改用 plus 控件�?win.ui.tabs 等，

这些控件可以支持适合缩放的字体图�?
### win.imageList.shell( _SHIL_ )

调用SHGetImageList获取系统图像列表

### win.imageList.shell()

[返回对象:imageListObject](#imageListObject)

## imagelistObject 成员列表

### imagelistObject.add

添加图像

### imagelistObject.add(图像路径,透明�?

添加图像,

成功返回自身,失败抛出异常

### imagelistObject.addBitmap

添加位图

### imagelistObject.addBitmap(位图句柄,透明�?

添加位图,

成功返回自身,失败抛出异常,

该函数会复制位图,不会接管或销毁传入的位图

如果传入的位图句柄不再使�?应使�?:DeleteObject销�?
### imagelistObject.addIcon

添加图标

### imagelistObject.addIcon(图标数据)

参数可指定图标数据或文件路径,支持资源路径,

成功返回自身,失败返回null

### imagelistObject.destroy()

删除对象

这个函数不会被在对象释放时被自动调用,

应用程序应在图像列表不再使用时调用此函数销毁对象，

注意treeview控件不负责自动销毁图像列表，

而listview控件在销毁时负责自动销毁正在使用的图像列表.

### imagelistObject.draw(索引,hDC,x,y,fStyle)

绘图

### imagelistObject.getIcon(索引,1/\*\_ILD\_TRANSPARENT\*/)

返回图标句柄

该句柄应使用 ::DestroyIcon 函数释放

### imagelistObject.height

高度

### imagelistObject.loadIcon(资源�?模块ID)

自图标资源载入图�?

参数@1可指定资源名或资源ID,

参数@2可省�?

成功返回自身,失败返回null

### imagelistObject.width

宽度

### 自动完成常量

\_ILC\_COLOR=0

\_ILC\_COLOR16=0x10

\_ILC\_COLOR24=0x18

\_ILC\_COLOR32=0x20

\_ILC\_COLOR4=4

\_ILC\_COLOR8=8

\_ILC\_COLORDDB=0xFE

\_ILC\_MASK=1

\_ILC\_MIRROR=0x2000

\_ILC\_PALETTE=0x800

\_ILC\_PERITEMMIRROR=0x8000

\_ILD\_ASYNC=0x8000

\_ILD\_BLEND25=2

\_ILD\_BLEND50=4

\_ILD\_DPISCALE=0x4000

\_ILD\_IMAGE=0x20

\_ILD\_MASK=0x10

\_ILD\_NORMAL=0

\_ILD\_OVERLAYMASK=0xF00

\_ILD\_PRESERVEALPHA=0x1000

\_ILD\_ROP=0x40

\_ILD\_SCALE=0x2000

\_ILD\_TRANSPARENT=1

\_ILS\_ALPHA=8

\_ILS\_GLOW=1

\_ILS\_NORMAL=0

\_ILS\_SATURATE=4

\_ILS\_SHADOW=2

\_SHIL\_EXTRALARGE=2

\_SHIL\_JUMBO=4

\_SHIL\_LARGE=0

\_SHIL\_SMALL=1

\_SHIL\_SYSSMALL=3

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/imageList.md)

