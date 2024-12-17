[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.aniBackground 库模块帮助文�?
## win.ui 成员列表

### win.ui.aniBackground

创建动画背景窗口,

建议窗体属性中开启双缓冲优化、以避免闪烁,

使用 win.ui.layered 也可以创建分层透明窗口

### win.ui.aniBackground()

[返回对象:winUiAniBackgroundObject](#winUiAniBackgroundObject)

### win.ui.aniBackground(winform,transparentColor)

创建动画背景窗口,

@winform 参数指定目标窗口,

可选用 @transparentColor 指定设为透明的颜�? 0xBBGGRR 格式,

使用 win.ui.layered 可直接支持图像透明�?
## winUiAniBackgroundObject 成员列表

### winUiAniBackgroundObject.add

添加动画�?
### winUiAniBackgroundObject.add("图像",延时)

图像格式支持 png,bmp,jpg,gif �?
如果要指定透明颜色,应使用无损格�?png �?bmp

### winUiAniBackgroundObject.animate()

播放动画

### winUiAniBackgroundObject.clear()

释放所有加载的图像

### winUiAniBackgroundObject.next()

返回下一帧位图句�?以及延时

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/aniBackground.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/aniBackground.md')

