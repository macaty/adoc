[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# win.image 库模块帮助文�?
## win.image 成员列表

### win.image.createAniCursor(动画光标数据)

自内存加载\*.ani格式的动画光�?
参数也可以是文件、或资源文件路径

### win.image.createIcon

在图标数据中加载指定像素的图�?失败返回空�?
### win.image.createIcon(图标数据,是否图标,适配大小,最大位�?选项)

自内存创建图�?失败返回空�?

图标数据:也可以是路径,或资源文件路�?

是否图标:可省�?默认为true,载入光标请指定为false,仅支持单色光�?
适配大小:可省�?如果不匹配则取最接近大小的图�?

最大位�?可省�?默认值为32�?
选项:保留参数,不必指定

如果选项不指定\_LR\_SHARED，返回的句柄不再使用时必须调�?::DestroyIcon销�?
### win.image.createSharedIcon(图标数据,是否图标,适配大小,最大位�?

自内存创建共享图�?失败返回空�?

图标数据:也可以是路径,或资源文件路�?

是否图标:可省�?默认为true,载入光标请指定为false,仅支持单色光�?
适配大小:可省�?如果不匹配则取最接近大小的图�?

最大位�?可省�?默认值为32�?
选项:保留参数,不必指定

\\返回的句柄不能调�?::DestroyIcon销�?注意这种图标不应大量创建

### win.image.extractIcon(EXE文件路径,图标索引,是否自动释放)

索引默认�?,如果�?,则返回图标总数,

参数二默认为true

### win.image.getIcon(窗口对象或句�?是否大图�?

获取窗口图标句柄

返回的句柄不应被释放,共享图标返回空�?
### win.image.loadCursor(请输入资源名,模块句柄)

自光标资源载入光�?

返回句柄无需释放

### win.image.loadCursorFromFile(位图路径)

自文件载入光�?支持资源文件

### win.image.loadIcon(请输入资源名,模块句柄)

自图标资源载入图�?

返回句柄无需释放

### win.image.loadIconFromFile(位图路径,是否自动释放)

自文件载入图�?支持aardio资源文件

参数二默认为true

### win.image.loadImage(请输入资源名,模块句柄)

自位图资源载入位�?

返回句柄无需释放

### win.image.loadImageFromFile(位图路径,是否自动释放)

自文件载入位�?支持aardio资源文件

参数二默认为true

### win.image.queryIconFromResource(图标数据,是否图标,回调函数,选项)

```aardio aardio
win.image.queryIconFromResource(/*图标数据或路�?/,true,

    function(count,index,width,height,bpp,colorCount,planes){
        if ( width == 48 & bpp == 32 ) {
            return true;
        }
    }
)

```

### win.image.setIcon(窗口对象或句�?图标句柄或路�?是否大图�?

设置窗口图标,窗口负责释放图标句柄,

参数@3设为true仅设置大图标,设为false仅设置小图标

如果省略参数@3则同时设置大图标和小图标�?
如果替换了小图标,返回�?为窗口原来的小图�?如果替换了大图标,返回�?为窗口原来的大图�?
[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/win/image.md)

