[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 窗体背景贴图

win.form 创建的窗体背景图做了�?plus 控件类似的缓存优化，但是要注意窗体绘制背景使用的�?GDI 而不�?GDI+，所以默认不支持 PNG 图像（改用分层窗口可以支持，不过一般窗口没必要这么做），可以支�?bmp,jpg,gif 等格�? bmp 格式的图像体积太大一般不建议使用�?
如果添加的图像在界面上显示不出来，请检查图像的后缀名是否正确。有一些图像后缀名是错误的，例如 jpg 文件使用 png 作为文件后缀名，这时候图像浏览器会自动修正这个问题，毕竟他们是专业干这事的。但我们自己写的程序要注意处理这个问题，毕竟我们自己才是开发者�?
## 使用九宫�?
参考： [九宫格布局与贴图](nine-grid.html)

我们创建窗体以后，在窗体设计器中点击窗体，然后在开发环境右侧的"属性面�?就可以直接设�?背景图像"属性了�?
设置好背景图像以后，可以启用九宫格模式�?
1. �?"属性面�? 设置 "九宫格切�? 属性为 true �?2. �?"属性面�? 设置 "切图位置" 设置切图坐标，然后\*\*滚动鼠标滚轮\*\*快速调整切图位置，窗体设计器会在窗体上实时绘制切图线条�?
所谓九宫格，就是按你设定的上、右、下、左四个坐标把图像划四条线切为九个格式，四个角的图像保持原来的大小显示在屏幕上，而其他中间的块则拉伸显示�?
固定自动拉伸固定拉伸自动拉伸拉伸固定自动拉伸固定

我们不仅仅是可以对整个窗口贴图、或以九宫格模式贴图�?
我们可以在窗体的任何一个区域单独贴背景图，并在区域内单独做九宫格拉伸。换句话说，我们可以单独为某个控件在窗体上绘制背景切图�?
方法是利用无句柄的背景贴图控件：bk �?bkplus 控件�?
bk 控件使用 GDI 绘图，bkplus 则与 plus 控件类似使用 GDI+ 绘图�?
bk,bkplus 实际上并不会创建任何窗口，作用仅仅是在窗体背景上划分出一块区域并指定切图效果。但�?bk,bkplus 控件像普通控件一样可以指定固定边距、自适应缩放这些效果�?
另外我们还可以利�?custom 控件，在窗口的任何一部分加载另一个窗�?—�?将窗体的任何一部分转换为其他窗体的容器�?
请参�?[《aardio 中最重要的控件：custom 控件使用指南》](ctrl/custom.html)

## 创建分层窗口

我们知道可以透明显示的分层窗口，是无法显示窗口上的控件子窗口的，但是使用标准库提供的 win.ui.layered，我们可以让分层窗口透明显示。win.ui.layered 不但支持 png 格式透明背景图，还可以正常的显示窗口上的 plus 控件。以下是一个简单的例子�?
```aardio aardio
import win.ui;
import win.ui.layered;
/*DSG{{*/
var winform = win.form(text="分层透明窗口";right=759;bottom=469)
winform.add(
plus={cls="plus";left=67;top=46;right=664;bottom=399;notify=1;repeat="scale";z=1}
)
/*}}*/

//创建分层透明窗口
win.ui.layered(winform);

//支持远程图像
import inet.http;

//背景动态显示玫瑰花图像
winform.plus.skin(
    background = {
        default = "https://download.aardio.com/demo/images/rose.png";
        hover = 0x6600FF33;
    }
)

winform.plus.oncommand = function(id,event){
    winform.close();
}

winform.show();
win.loopMessage();

```

上面的示例用了网络图像，下载图像需要时间，实际开发请使用本地图像�?
## 创建不规则窗�?
如果窗窗体设置了一个很酷的不规则背景图，我们可以按如下步骤让窗体本身也自动变成不规则形状�?
- 右键点击窗体，在弹出菜单中首先点击【调整为背景图大小】�?- 再次在菜单中点击【创建不规则窗口】将会生成下面的代码�?

  ```aardio aardio
  import win.region.bitmap;
  win.region.bitmap( winform )

  ```


  很简单这两句代码就可以实现不规则窗口了�?

注意 win.region.bitmap 只是对图像做简单的分析，运行时处理图像不是我们所需要的�?
所以我们需要了解一些规则，图像是深色的、背景就应当是浅色的，图像是浅色的背景则应当是深色的，如果处理后的图像有杂边�?�?win.region.bitmap(winform 参数后面输入逗号，然后注意看编辑器自动弹出的参数提示，反复调整最后一个参数（�?0x101010 �?0x303030 之间调整出最佳效果）

也可以另外做一个黑白对比的掩码图更明确的标明背景取代背景图来创建不规则窗口，这会有更好的效果，示例代码如下:

```aardio aardio
import win.region.bitmap;

win.region.bitmap("/res/winform.regin.jpg").updateWindow(winform.hwnd)

```

制作掩码图很简单，使用 Photoshop 建立图像，双击背景转换为图层并在编辑菜单中选择【填充】为白色�?
然后按住CTRL键点击前景图层在前景图像上创建选框，删除图像并填充为黑色即可�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/background.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/background.md')
