[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 绘图基础

```aardio aardio
//窗口程序 - 绘图基础
/*
对于绘图大致了解一些基础的概念就可以�?学习 aardio 并不是一定要深入学习这些内容，大多时候不需要自己绘图�?
�?绘图接口
—————————————————————————————————————————————————————————————�?1、GDI(Graphics Device Interface)

GDI 是基础的绘图接口�?标准�?gdi 用于 GDI 绘图操作�?传统的窗口控件默认使�?GDI 绘图�?
2、GDI+

GDI+ 是新版绘图接口，扩展�?GDI 的功能�?标准�?gdip 用于 GDI+ 绘图操作�?plus 控件基于 gdip（GDI+）�?GDI+ 参考手�? https://learn.microsoft.com/zh-cn/windows/win32/gdiplus/-gdiplus-gdi-start

�?图像
—————————————————————————————————————————————————————————————�?1、GDI 位图

GDI 位图与图标与其他系统资源一样通过句柄操作，句柄是一个指针类型的值�?使用位图句柄要仔细查看相关函数的文档，了解什么时候需要手动释放位图�?可使�?::DeleteObject(hBmp) 释放位图（参�?hBmp 为位图句柄）�?
2、com.picture 对象

com.picture 可加�?JPG,GIF,BMP 等图像，
调用 com.picture 对象�?CopyHandle() 函数可以复制位图并返回位图句柄�?调用 com.picture.fromBitmap() 函数可将位图句柄转换�?com.picture 对象�?picturebox 控件使用 com.picture 加载图像并获取位图句柄�?com.picture 对象会在不需要时自动回收，可选用 com.Release() 函数主动释放�?
3、gdip.bitmap 对象

gdip.bitmap 用于创建GDI+ 位图对象�?可用于加载常用图像格�?例如 JPG,GIF,BMP，并且支�?PNG�?调用 gdip.bitmap 对象�?copyHandle() 函数可以复制位图并返回位图句柄�?调用 gdip.bitmap 构造函数可将参�?@1 指定的位图句柄转换为 gdip.bitmap 对象�?调用 gdip.bitmap 构造函数可将参�?@1 指定�?com.picture 对象转换�?gdip.bitmap 对象�?
实际�?aardio 程序用得最多的�?GDI+ �?plus 控件，绘图范例也主要是使�?GDI+�?除了操作剪贴板之类传统接口，很少需�?gdip.bitmap、com.picture、位图句柄相互转换的操作�?
gdip.bitmap 对象会在不需要时自动回收，可选用对象的成员函�?dispose() 主动释放

�?颜色格式
—————————————————————————————————————————————————————————————�?1、用�?GDI �?RGB 颜色�?
RGB 颜色值一般用�?GDI 接口（aardio 标准库：gdi），以及标准控件�?
RGB 颜色值可�?6 �?16 进制数�?0xBBGGRR 表示�?BB 表示蓝色（blue）分量，GG 表示绿色（green)分量，RR 表示红色(red)分量�?
例如 0xFF0000 表示蓝色�?
RGB 颜色值在内存存储格式用字符串表示就是 '\xRR\xGG\xBB'�?�?结构体表示就�?{ BYTE r;  BYTE g;  BYTE b; }
存储顺序都是低位在前�?
数值的存储顺序同样是低位在前，也就是小端字节序（这样记：低位在前，小端在前�?但书写数值顺序是高位在前，所�?RGB 颜色值写为数值就�?0xBBGGRR�?
�?Windows �?GDI 头文件中表示此颜色值的定义�?COLORREF �?RGB �?
2、用�?GDI+ �?ARGB 颜色�?
ARGB 颜色值用�?GDI+ 接口（aardio 标准库：gdip），以及基于 GDI+ �?plus 控件�?
ARGB 颜色可用 8 �?16 进制数�?0xAARRGGBB 表示�?AA 表示 Alpha 值，Alpha 值影响的是透明度，其他表示 RGB 分量�?
例如 0xFFFF0000 表示不透明红色�?
ARGB 颜色值在内存存储格式用字符串表示就是 '\xBB\xGG\xRR\xAA'�?用结构体表示就是 { BYTE b;BYTE g;BYTE r;BYTE a; }
数值的书写顺序是反过来的，所以写�?0xAARRGGBB �?
那么为什么叫 ARGB 颜色值，而不�?BGRA 颜色值呢�?一定要找个理由就是念着顺口，GDI+ 头文件就是这样命名，约定俗成就是规则�?纠结这个正反顺序，就好比纠结『东西』为什么不叫『西东』一样毫无意义�?
�?Windows �?GDI+ 头文件中 ARGB 类型被定义为 DWORD 类型的别�?—�?对应 aardio 原生类型中的 INT 类型�?
在用 aardio 调用 .NET 时，.NET 里的 System.Drawing.Color 颜色值在 aardio 中也会被自动转换�?ARGB 格式颜色数值）�?
3、字符串格式

aardio 提供 gdi.colorParse() 函数可解析网页兼容的、用字符串表示的颜色代码�?支持 #RGB�?RRGGBB�?RRGGBBAA 三种格式�?号可省略�?
#RGB�?RRGGBB 返回 GDI 兼容�?RGB 值�?#RRGGBBAA 返回 GDI+ 兼容�?ARGB 格式颜色值�?
现代浏览器，HTMLayout，Sciter 等浏览器组件可支�?#RRGGBBAA 格式颜色值，IE 浏览器组件不支持 #RRGGBBAA �?
也可以用 gdi.colorStringify() 将颜色值转换为字符串格式�?*/
import win.ui;
/*DSG{{*/
var winform = win.form(text="颜色格式";right=759;bottom=469)
winform.add(
plus={cls="plus";left=192;top=277;right=542;bottom=360;font=LOGFONT(h=-32);z=1};
static={cls="static";text="Static";left=192;top=98;right=542;bottom=181;align="center";center=1;font=LOGFONT(h=-32);z=2}
)
/*}}*/

//-------------- GDI / 传统控件 --------------

//标准控件的背景色设为 RGB 颜色，格�?0xBBGGRR
winform.static.bgcolor = 0xFF0000;//蓝色

//获取 R,G,B 分量，参数为 RGB 颜色�?var r,g,b = gdi.getRgb(0xFF0000);
//函数�?gdi.getRgb �?get R,G,B 的缩写�?
//R,G,B 分量转换�?RGB 颜色数值（0xBBGGRR�?winform.static.bgcolor = gdi.RGB(r,g,b);

//用字符串转换�?RGB 颜色数�?winform.static.bgcolor = gdi.colorParse("#0000FF");

//颜色值转换为字符�?winform.static.text = gdi.colorStringify(0xFF0000,false);

//字体颜色设为白色
winform.static.color = 0xFFFFFF;

//-------------- GDI+ / plus 控件 --------------

//plus 控件的背景色设为 ARGB 颜色，格�?0xAARRGGBB
winform.plus.background = 0xFFFF0000;

//获取 R,G,B,A 分量，参数为 ARGB 颜色值�?var r,g,b,a = gdi.getRgba(0xFFFF0000)
//函数�?gdi.getRgba �?get R,G,B,A 的缩写�?
//R,G,B 分量转换�?RGB 颜色数值（0xBBGGRR�?winform.plus.background = gdi.ARGB(r,g,b,a);

//用字符串转换�?ARGB 颜色数�?winform.plus.background = gdi.colorParse("#FF0000FF");

//颜色值转换为字符�?winform.plus.text = gdi.colorStringify(0xFFFF0000,true)

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/QuickStart.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/QuickStart.md')

