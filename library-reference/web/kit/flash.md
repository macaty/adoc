[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.kit.flash 库模块帮助文�?
## web.kit.flash 成员列表

�?web.kit.form 加载 Flash

### web.kit.flash.transparent()

[返回对象:wkeFlashObject](#wkeFlashObject)

### web.kit.flash.transparent(winform,param)

嵌入透明 FLASH 控件,

参数@1为窗体或控件对象

可选在参数@2中使用一个表对象设定Flash控件的属性�?
## web.kit 成员列表

### web.kit.flash()

[返回对象:wkeFlashObject](#wkeFlashObject)

### web.kit.flash(winform,param)

嵌入 FLASH 控件,

参数@1为窗体或控件对象

可选在参数@2中使用一个表对象设定Flash控件的属性�?
## wkeFlashObject 成员列表

### wkeFlashObject.\_form

窗体对象

[返回对象:winform](../../win/ui/_.html#winform)

### wkeFlashObject.\_host

容器对象

### wkeFlashObject.\_host.adjust()

调整控件窗口大小

### wkeFlashObject.\_object

控件对象

### wkeFlashObject.allowFullScreen

布尔�?是否允许全屏

### wkeFlashObject.allowNetworking

是否允许网络交互,可选�?

"all","internal","none"

### wkeFlashObject.allowScriptAccess

是否允许调用外部脚本,可选�?

"always","sameDomain","never"

### wkeFlashObject.back()

影片后退一帧并停止播放

### wkeFlashObject.bgcolor

背景�?
�?#RRGGBB"格式的文本表�?
### wkeFlashObject.body

网页 body 元素 HTML 代码节点,

修改此元素属性后需要调�?render 函数才会生效

[返回对象:eleObject](#eleObject)

### wkeFlashObject.currentFrame()

当前帧索�?注意第一帧索引为0

### wkeFlashObject.disableLocalSecurity()

禁用本地安全,

请不要在播放动画以后调用此函�?

播放的swf是程序自带的可信任文件时应当禁用本地安全

当指定控件的external接口时也会自动调用此函数

### wkeFlashObject.embedMovie

该值如果为true则允许在加载后删除swf文件

### wkeFlashObject.enforceLocalSecurity()

启用本地安全,

请不要在播放动画以后调用此函�?

如果播放的swf是程序自带的可信任文件应当启用本地安�?
### wkeFlashObject.external

```aardio aardio
wkeFlashObject.external = {
    函数�?= function(参数){
        /*在FLASH中可使用 ExternalInterface.call() 调用这里的函�?/
        return "返回�?;
    }
}

```

### wkeFlashObject.flashVars

等价于parameters属�?参考该属性说�?
### wkeFlashObject.forward()

影片后退一帧并停止播放

### wkeFlashObject.getPersistStream()

返回数据流对�?
[返回对象:IPersistStreamInitObject](#IPersistStreamInitObject)

### wkeFlashObject.getVariable("字符串参�?)

获取FLASH变量

### wkeFlashObject.gotoFrame(索引)

将影片跳转到指定的帧并停止播�?

必须首先调用percentLoaded()函数保证影片完全加载

### wkeFlashObject.hwndControl

Flash控件窗口句柄

### wkeFlashObject.loadMovie(layer,url)

将由url指定的影片载入到由layer指定的层�?
如果url指定了一个资源文件路�?使用临时文件加载,并设置embedMovie属性为 true

### wkeFlashObject.loop

是否循环播放

### wkeFlashObject.menu

右键是否显示Flash控制菜单

### wkeFlashObject.movie

设置swf文件网址,

参数必须是网址,

本地文件建议使用 wsock.tcp.simpleHttpServer.startUrl 转换为网址

### wkeFlashObject.pan(x,y,mode)

将一个放大过的影片平移由x和y指定的距�?x和y均为相对�?

mode默认值为1,按百分比计算,如果设为0则以像素计算

### wkeFlashObject.parameters

设置初始化参�?也就是AS里的loaderInfo.parameters,

参数格式与URL参数相同,设置一个表参数可自动转换为字符�?

读取属性时返回字符�?
### wkeFlashObject.percentLoaded()

返回影片加载的百分比

### wkeFlashObject.play()

播放

### wkeFlashObject.playing

影片是否正在播放

### wkeFlashObject.putMovie("/res/ui.swf")

加载Flash文件,

参数可以是网址,文件�?支持内嵌资源目录文件�?
参数也可以是Flash文件的内存数�?
加载内存或资源文件时,直接调用write函数写入内存

### wkeFlashObject.quality

获取设置影片质量,可选使用以下字符串表示�?

"Low":偏重于播放速度而不管显示效�?

"High":偏重于画面而不管播放速度

"AutoLow":先着重于播放速度,但只要有可能就改善显示效�?

"AutoHigh":一开始是播放速度和显示效果并�?但如有必要就牺牲画质确保速度.

### wkeFlashObject.readyState

返回影片的当前状�?readyState值有:

0:正在载入

1:未初始化

2:已载�?
3:正在交互

4:完成例子

### wkeFlashObject.render()

更新属性并重新创建 Flash 控件,

修改 Flash 控件属性后需要调用此函数才会生效,

修改 movie 属性自动调用此函数

### wkeFlashObject.rewind()

返回到影片的第一�?
### wkeFlashObject.sAlign

使用字符串表示对�?

"L":即左对齐

"T":即顶对齐

"R":即右对齐

"B":即底对齐

上面的值可组合使用,但LTRB的先后顺序不能变,�?左和底的对齐必须写为"LB"

### wkeFlashObject.scale

缩放模式:

"NoScale":显示原始大小不缩�?

"ShowAll":显示全部影片区域,保持影片长宽比例不变.

"NoBorder":显示部分影片区域,保持影片长宽比例不变.

"ExactFit":显示全部影片区域,强制将影片的长宽等于控件的长�?

### wkeFlashObject.setVariable("变量�?,�?

设置FLASH变量

### wkeFlashObject.show()

显示Flash所在窗�?
### wkeFlashObject.stop()

暂停

### wkeFlashObject.swfObject

网页 Flash 控件 HTML 代码节点,

修改此元素属性后需要调�?render 函数才会生效

[返回对象:eleObject](#eleObject)

### wkeFlashObject.totalFrames

返回影片总帧�?
### wkeFlashObject.translateUrl

```aardio aardio
wkeFlashObject.translateUrl = function(url){
    /*可在此函数中转换 movie 属性传入的 URL 参数
也可以直接使�?wsock.tcp.simpleHttpServer.startUrl 等函�?/
    return url;
}

```

### wkeFlashObject.transparent

是否启用透明模式,只写属�?

应当写在初始化参数中

### wkeFlashObject.version

flash控件版本

### wkeFlashObject.wMode

控件的窗口模�?可选�?Window","Opaque","Transparent"

### wkeFlashObject.wait()

等待影片加载完成

### wkeFlashObject.wait(true)

等待影片播放完成

### wkeFlashObject.wke

浏览器对�?
[返回对象:webKitViewObject](#webKitViewObject)

### wkeFlashObject.write()

直接通过写入内存数据重新加载swf文件

### wkeFlashObject.writeStream()

写入数据�?
参数应是fsys.strem等兼容IStream接口的对�?
### wkeFlashObject.xcall("FLASH函数�?,其他参数)

调用FLASH中使用ExternalInterface.addCallback()导出的函�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/kit/flash.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/kit/flash.md')

