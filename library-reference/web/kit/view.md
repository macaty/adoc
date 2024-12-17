[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# web.kit.view 库模块帮助文�?
## 全局对象 成员列表

### wkeWebView

[返回对象:webKitViewObject](#webKitViewObject)

## web.kit 成员列表

### web.kit.view

webkit视图

### web.kit.view()

创建WebKit视图,

如果不指定参数视图不负责创建显示窗口,

如果在参数中直接指定一个窗口对�?则创建默认的显示窗口,

控件创建的窗口句柄可通过hWkeWindow属性获�?
[返回对象:webKitViewObject](#webKitViewObject)

## webKitViewObject 成员列表

### webKitViewObject.\_form

浏览器宿主窗�?
[返回对象:staticObject](../../win/ui/ctrl/static.html#staticObject)

### webKitViewObject.addDirtyArea(x,y,w,h)

设置无效区域

### webKitViewObject.attach

```aardio aardio
webKitViewObject.attach(
    function(event){
        io.print("点击坐标", event.screenX,event.screenY )
        io.print("触发节点", event.srcElement.innerText )
    }
    ,"onclick",ele/*也可输入getEle()所需参数,省略表示doc*/
)

```

### webKitViewObject.attachAll

```aardio aardio
webKitViewObject.attachAll(
    /* html节点ID = 事件触发函数�?*/
    caption_button_min = {
        onclick = function(event){
            wb._form.hitmin();
        }
    }
)

```

### webKitViewObject.canGoBack()

能否后退

### webKitViewObject.canGoForward()

能否前进

### webKitViewObject.click(控件名字,随机延时最小�?延时最大�?框架�?

模拟点击控件,

第一个参数也可以是ele对象,

随机延时值为可选参�?默认�?,500.

框架名为可选参�?
### webKitViewObject.contextMenuEvent(x,y,flags)

转发右键菜单事件到网�?
x,y 参数为相对于窗口左上角的坐标�?

flags 参数为\_WKE\_前缀常量,可省�?支持的选项如下

\_WKE\_CONTROL 表示按下Ctrl键\_WKE\_SHIFT 表示按下Shift�?
\_WKE\_LBUTTON 表示按下鼠标左键

\_WKE\_MBUTTON 表示按下鼠标左键

\_WKE\_RBUTTON 表示按下鼠标右键

多个选项�?\| 连接

不指定则默认为\_WKE\_RBUTTON

### webKitViewObject.cookie

返回网页cookie，文�?
### webKitViewObject.cookieClear()

清空cookie

### webKitViewObject.cookieClearSession()

清空会话cookie

### webKitViewObject.cookieData()

返回所有cookie,返回值为fsys.cookies对象

[返回对象:fsyscookiesObject](#fsyscookiesObject)

### webKitViewObject.cookieEnabled

是否允许使用cookie

### webKitViewObject.cookieReload()

自文件重新载入cookie

### webKitViewObject.cookieSave()

保存cookie

### webKitViewObject.cookieSet()

设置cookie,

参数可以是单个cookie的字段键值对组成的表,

也可以是符合HTTP响应头中设置Cookie格式相同的字符串

也可以指定fsys.cookies对象

了解cookie格式的细节，请查看fsys.cookies�?
### webKitViewObject.copy()

复制

### webKitViewObject.cut()

剪切

### webKitViewObject.delete()

删除

### webKitViewObject.destroy()

销毁对�?
### webKitViewObject.dispatchEvent("字符串参�?,"click")

触发事件

### webKitViewObject.doScript(js代码)

执行JS脚本

### webKitViewObject.document

Javascript网页文档对象

document.

### webKitViewObject.enumCookie

```aardio aardio
webKitViewObject.enumCookie(
    function(sData,pData){
        /*pData为cookie指针,sData为Cookie文本*/
    }
)

```

### webKitViewObject.eval(JS表达�?

计算JS表达式并返回�?
### webKitViewObject.external

```aardio aardio
webKitViewObject.external = {
    /*external的成员函数可在JS中调�?/
};

```

### webKitViewObject.flash

获取默认的或 name 属性为 plugin �?Flash NPAPI 插件对象

直接打开 \*.swf 文件时会自动创建此对�?
[返回对象:webNpPluginFlashObject](#webNpPluginFlashObject)

### webKitViewObject.focus()

设置焦点

### webKitViewObject.getContentsHeight()

文档高度

### webKitViewObject.getContentsWidth()

文档宽度

### webKitViewObject.getForm()

返回该视图所在窗体对�?
[返回对象:winform](../../win/ui/_.html#winform)

### webKitViewObject.getForm(false)

返回该视图所在窗口或控件对象

### webKitViewObject.getHeight()

视图高度

### webKitViewObject.getWidth()

视图宽度

### webKitViewObject.go("字符串参�?)

打开网址

如果导入 web.npPlugin.flash 则支持输�?swf 文件网址

### webKitViewObject.goBack()

后退

### webKitViewObject.goForward()

前进

### webKitViewObject.hWkeWindow

如果在创建web.kit.view对象时指定了父窗口参�?并由WKE创建控件显示窗口

此属性返回WKE创建的窗口句�?
### webKitViewObject.html

```aardio aardio
webKitViewObject.html = /**
<!doctype html>
<html>
<head>
    <style type="text/css">
    html,body{ height:100%; margin:0; }
    </style>
    <script type="text/javascript"></script>
</head>
<body>
    <div id="header"></div>
    <div id="container">
        <div class="lside"> </div>
        <div class="rside"> </div>
    </div>
</body>
</html>
**/

```

### webKitViewObject.isAwake()

是否运行

### webKitViewObject.isDirty()

是否需要重�?
### webKitViewObject.isDocumentReady()

文档对象是否准备就绪

### webKitViewObject.isLoadComplete()

是否加载完成

即isLoaded或isLoadFailed函数返回true

### webKitViewObject.isLoadFailed()

是否加载失败

### webKitViewObject.isLoaded()

是否加载成功

### webKitViewObject.jQuery("字符串参�?)

jQuery选择�?并可自动载入jQuery�?
n首次调用按需加载jQuery v1.9:

"/res/js/jQuery/jQuery.min.js"

失败则通过网络CDN服务器下载jquery-1.9.0.min.js

### webKitViewObject.jQuery()

无参数时返回jQuery类对�?
首次调用按需加载 jQuery v1.9:

"/res/js/jQuery/jQuery.min.js"

失败则通过网络CDN服务器下载jquery-1.9.0.min.js

[返回对象:jQueryObject](#jQueryObject)

### webKitViewObject.keyDown(vkCode,flags,sysKey)

转发按键释放事件到网�?
vkCode 参数指定虚拟键码,请参考标准库key.VK

flags 参数可用指定一个或多个以下选项:

\_WKE\_REPEAT表示重复按键,

\_WKE\_EXTENDED表示扩展�?

多个选项�?\| 连接

sysKey 参数指定是否同时按下ALT�?

### webKitViewObject.keyPress(charCode,flags,sysKey)

转发WM\_CHAR事件到网�?
charCode 参数指定字符代码,

flags 参数可用指定一个或多个以下选项:

\_WKE\_REPEAT表示重复按键,

\_WKE\_EXTENDED表示扩展�?

多个选项�?\| 连接

sysKey 参数指定是否同时按下ALT�?

### webKitViewObject.keyUp(vkCode,flags,sysKey)

转发按键释放事件到网�?
vkCode 参数指定虚拟键码,请参考标准库key.VK

flags 参数可用指定一个或多个以下选项:

\_WKE\_REPEAT表示重复按键,

\_WKE\_EXTENDED表示扩展�?

多个选项�?\| 连接

sysKey 参数指定是否同时按下ALT�?

### webKitViewObject.load( filename)

加载文件

### webKitViewObject.loadScript("js地址","字符串参�?,"utf-8")

动态加载js文件\\N可选用第三个参数指定文件编�?
### webKitViewObject.location

当前网址

### webKitViewObject.mediaVolume

音量,范微0.0�?.0

### webKitViewObject.mouseEvent(message,x,y,flags)

转发鼠标事件到网�?
message为\_WM\_前缀的窗口鼠标消息常�?
x,y 参数为相对于窗口左上角的坐标�?

flags 参数为\_WKE\_前缀常量,可省�?支持的选项如下

\_WKE\_CONTROL 表示按下Ctrl键\_WKE\_SHIFT 表示按下Shift�?
\_WKE\_LBUTTON 表示按下鼠标左键

\_WKE\_MBUTTON 表示按下鼠标左键

\_WKE\_RBUTTON 表示按下鼠标右键

多个选项�?\| 连接

不指定则默认为\_WKE\_LBUTTON

### webKitViewObject.mouseWheel(x,y,delta,flags)

转发滚轮事件到网�?
x,y 参数为相对于屏幕左上角的坐标�?

delta�?20的倍数,负数向下滚动,正数向上滚动,

flags 参数为\_WKE\_前缀常量,可省�?支持的选项如下

\_WKE\_CONTROL 表示按下Ctrl键\_WKE\_SHIFT 表示按下Shift�?
\_WKE\_LBUTTON 表示按下鼠标左键

\_WKE\_MBUTTON 表示按下鼠标左键

\_WKE\_RBUTTON 表示按下鼠标右键

多个选项�?\| 连接

不指定则默认为\_WKE\_MBUTTON

### webKitViewObject.onAlertBox

```aardio aardio
webKitViewObject.onAlertBox = function(str){
    /*alert对话框触发此事件,返回true不显示默认对话框*/
    return true;
}

```

### webKitViewObject.onConfirmBox

```aardio aardio
webKitViewObject.onConfirmBox = function(str){
    /*确认对话框触发此事件,
定义此事件后不再显示确认对话�?可在这里修改返回�?/
   return result;
}

```

### webKitViewObject.onDocumentReady

```aardio aardio
webKitViewObject.onDocumentReady = function(url,mainFrameJSState,frameJSState){
    if( mainFrameJSState == frameJSState ){
        /*主框架加载完�?/
    }
}

```

### webKitViewObject.onNavigation

```aardio aardio
webKitViewObject.onNavigation = function(url,navigationType){
    if( navigationType == _WKE_NAVIGATION_TYPE ){

    }
    return true;
}

```

### webKitViewObject.onPromptBox

```aardio aardio
webKitViewObject.onPromptBox = function(title, default){
    /*输入对话�?可选返回输入的字符�?title为标�?default为默认显示在输入框的文本*/
    return;
}

```

### webKitViewObject.onTitleChanged

```aardio aardio
webKitViewObject.onTitleChanged = function(title){
    owner.getForm().text = title;
}

```

### webKitViewObject.onURLChanged

```aardio aardio
webKitViewObject.onURLChanged = function(url){
    if(#url) owner.getForm().msgbox( url )
}

```

### webKitViewObject.paint(bits,pitch)

绘图,参数@1为位图像素数组指�?
关于这个函数的用法请参考web.kit.gdiRender

### webKitViewObject.paste()

复制

### webKitViewObject.plugin

获取默认的或 name 属性为 plugin �?NPAPI 插件对象

### webKitViewObject.post(网址,POST数据)

POST提交数据

### webKitViewObject.print(hdc,scale)

用于GDI打印输出,hdc为打印机设备DC�?
scale指定缩放比例,正数为缩放文�?负数按输出页面缩�?
例如-0.5为缩放至页面�?0%

### webKitViewObject.queryEles

搜索节点对象,该函数返回的是一个数�?

但可以通过调用数组的成员函数批量调用节点的同名成员函数,支持click函数,

即使找不到节�?此函数也会返回一个空数组,

### webKitViewObject.queryEles()

[返回对象:eleObject](#eleObject)

### webKitViewObject.queryEles(CSS选择�?查询参数�?超时�?

搜索节点对象,该函数返回的是一个数�?

但可以通过调用数组的成员函数批量调用节点的同名成员函数,支持click函数

参数@1指定一个表对象�?
该参数表可包含一个或多个键值，用于匹配节点的属性�?

属性值使�?string.cmpMatch函数进行比对�?
等价于调用string.cmp函数进行忽略大小写的比较,

并且在失败后调用 string.match函数使用模式匹配语法进行比较�?
注意在匹配节点属性时有几个例外：

tagName,id,name属性如果匹配值不含标点则使用忽略大小写的完全比对（禁用模式匹配和部分匹配�?
可选使用参数@2指定获取网页文档对象的超时值，单位毫秒，此参数一般不需要指�?
### webKitViewObject.querySelector("CSS选择�?)

查询并返回节�?
### webKitViewObject.querySelector()

[返回对象:eleObject](#eleObject)

### webKitViewObject.querySelectorAll("CSS选择�?)

查询并返回节点集�?length属性获取节点个�?
### webKitViewObject.querySelectorAll()

[返回对象:eleObject](#eleObject)

### webKitViewObject.reload()

重新载入

### webKitViewObject.resize(w,h)

调整大小

### webKitViewObject.script

Javascript全局对象

[返回对象:jsGlobalObject](#jsGlobalObject)

### webKitViewObject.select("控件名字",/\*输入选项索引,或选项值、选项文本\*/)

查找下拉选框的指定选项,选中并返回选项节点

第一个参数也可以是ele对象

### webKitViewObject.selectAll()

全�?
### webKitViewObject.setDirty(dirty)

设置是否需要重�?
### webKitViewObject.setEditable(editable)

设置编辑状�?
### webKitViewObject.setEle(控件名字,属性�?属性名)

更新控件�?成节返回节点,失败返回null空�?
第一个参数也可以是ele对象,

属性名,框架名为可选参�?

属性值可以是一个指定多个属性键值对的table对象

### webKitViewObject.sleep()

休眠

### webKitViewObject.stopLoading()

停止加载

### webKitViewObject.translateUrl

```aardio aardio
webKitViewObject.translateUrl = function(url){
    /*可在此函数中转换 go 函数传入�?URL 参数*/
    return url;
}

```

### webKitViewObject.transparent

背景是否透明

不透明则使用白色背�?
### webKitViewObject.unfocus()

取消焦点

### webKitViewObject.userAgent

设置User Agent

### webKitViewObject.wait

该函数等待网页完全加载完�?

因为部份网页遇到问题可能部份内容无法完全加载,

建议大家尽可能使用等待部份加载的waitEle或waitDoc等函数替�?
### webKitViewObject.wait("网址",超时�?

等待指定的网页加载完�?所有参数可�?

等待的网址支持模式语法,参数@2指定最大超时�?单位毫秒

### webKitViewObject.waitDoc()

等待文档对象准备就绪,并返回文档对�?
document.

### webKitViewObject.waitEle("ID或名�?,,超时�?

返回一个节点对�?除参数一以外,其他能数可�?
第三个参数指定超时�?单位为毫�?

参数@2必须为空

### webKitViewObject.waitQueryEles

函数等待queryEles()返回有效节点,

即使找不到节�?此函数也会返回一个空数组,

web窗体关闭或超时返回null空�?
### webKitViewObject.waitQueryEles()

[返回对象:eleObject](#eleObject)

### webKitViewObject.waitQueryEles(CSS选择�?查询参数�?超时�?时间间隔,节点完全加载)

函数等待wb.queryEles()返回有效节点,

web窗体关闭或超时返回null空�?
该函数返回的是一个数�?但可以通过调用数组的成员函�?
批量调用节点的同名成员函�?支持click函数

参数@1指定一个表对象�?
该参数表可包含一个或多个键值，用于匹配节点的属性�?

属性值使�?string.cmpMatch函数进行比对�?
等价于调用string.cmp函数进行忽略大小写的比较�?
并且在失败后调用 string.match函数使用模式匹配语法进行比较�?
注意在匹配节点属性时有几个例外：

tagName,id,name属性如果匹配值不含标点则使用忽略大小写的完全比对（禁用模式匹配和部分匹配�?
可选使用参数@2指定超时值，单位毫秒�?其他参数可�?
### webKitViewObject.wake()

恢复运行

### webKitViewObject.window

Javascript全局对象

[返回对象:jsGlobalObject](#jsGlobalObject)

### webKitViewObject.wndproc(hwnd,message,wParam,lParam)

处理窗口消息

返回值为真表示不再需要后续默认消息处�?
### webKitViewObject.write(html)

写入HTML,如果参数@1不是字符串、buffer、null 则自动转为字符串

### webKitViewObject.zoomFactor

缩放百分�?
浮点�?1.0为实际大�?
## webNpPluginFlashObject 成员列表

### webNpPluginFlashObject.Back()

影片后退一帧并停止播放

### webNpPluginFlashObject.CurrentFrame()

当前帧索�?注意第一帧索引为0

### webNpPluginFlashObject.Forward()

影片后退一帧并停止播放

### webNpPluginFlashObject.GetVariable("$version变量�?)

获取FLASH变量

### webNpPluginFlashObject.GotoFrame(索引)

将影片跳转到指定的帧并停止播�?

必须首先调用percentLoaded()函数保证影片完全加载

### webNpPluginFlashObject.IsPlaying()

是否正在播放动画

### webNpPluginFlashObject.LoadMovie(layer,url)

将由url指定的影片载入到由layer指定的层�?
如果url指定了一个资源文件路�?使用临时文件加载,并设置embedMovie属性为 true

### webNpPluginFlashObject.Pan(x,y,mode)

将一个放大过的影片平移由x和y指定的距�?x和y均为相对�?

mode默认值为1,按百分比计算,如果设为0则以像素计算

### webNpPluginFlashObject.PercentLoaded()

返回影片加载的百分比

### webNpPluginFlashObject.Play()

播放

### webNpPluginFlashObject.Rewind()

返回到影片的第一�?
### webNpPluginFlashObject.SetVariable("变量�?,�?

设置FLASH变量

### webNpPluginFlashObject.SetZoomRect(left,top,right,buttom)

放大指定区域

### webNpPluginFlashObject.Stop()

暂停

### webNpPluginFlashObject.TCallFrame(movieClip,frame\_number)

call指定帧上的action

### webNpPluginFlashObject.TCallLabel(movieClip,label)

call指定标签上的action

### webNpPluginFlashObject.TCurrentFrame(movieClip)

回传movieClip当前�?1

### webNpPluginFlashObject.TCurrentLabel(movieClip)

回传movieClip当前标签

### webNpPluginFlashObject.TGetProperty(movieClip,property)

获取movieClip的指定属�?
### webNpPluginFlashObject.TGotoLabel(movieClip,label\_name)

movieClip跳转到指定标�?
### webNpPluginFlashObject.TPlay(movieClip)

播放movieClip

### webNpPluginFlashObject.TSetProperty(movieClip,property,number)

设置movieClip的指定属�?
### webNpPluginFlashObject.TStopPlay(movieClip)

停止movieClip的播�?
### webNpPluginFlashObject.TotalFrames()

返回影片总帧�?
### webNpPluginFlashObject.Zoom(percent)

改变动画大小

### webNpPluginFlashObject.getAttribute(name)

获取节点属�?
### webNpPluginFlashObject.setAttribute(name,value)

设置节点属�?

相当于在HTML里写属性�?
### 自动完成常量

\_WKE\_CONTROL=8

\_WKE\_EXTENDED=0x100

\_WKE\_LBUTTON=1

\_WKE\_MBUTTON=0x10

\_WKE\_NAVIGATION\_TYPE\_BACKFORWARD=2

\_WKE\_NAVIGATION\_TYPE\_FORMRESUBMITT=4

\_WKE\_NAVIGATION\_TYPE\_FORMSUBMITTE=1

\_WKE\_NAVIGATION\_TYPE\_LINKCLICK=0

\_WKE\_NAVIGATION\_TYPE\_OTHER=5

\_WKE\_NAVIGATION\_TYPE\_RELOAD=3

\_WKE\_RBUTTON=2

\_WKE\_REPEAT=0x4000

\_WKE\_SHIFT=4

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/kit/view.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ �������������ʵ��ļ������صġ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/kit/view.md')

