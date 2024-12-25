[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 创建 Web 窗体

## 什么是 Web 窗体

Web 窗体可以存取控制网页内容，并可以与网页内容进行交互，Web 窗体可以实现以下功能�?
1. 浏览并控制网�?

   使用 Web 窗体可以显示网页，并自由读取、修改、控制网页内容。也可以在网页中使用脚本调用aardio 代码�?
2. 使用网页设计漂亮的图形用户界�? GUI )


   使用 Web 窗体，你可以通过编写网页轻松实现自定义的程序界面�?

## 创建 Web 窗体工程

- 点击主菜单『创建工程�?
- 在打开的工程向导中点击�?Web 界面 』，然后选择�?Web Form �?工程�?
- 点击『创建工程』按钮�?

## 编辑 Web 窗体源代�?
打开 Web 窗体,点击"代码视图",或按 Ctrl+U 快捷键打开 Web 窗体源代�?

```aardio aardio
import win.ui;
import web.form;

/*DSG{{*/
var winform = win.form( bottom=249;scroll=1;text="aardio Form";right=349)
/*}}*/

//创建 Web 窗体
var wb = web.form( winform );

//打开目标网站
wb.go("http://www.aardio.com/")

//显示窗体
winform.show(true)
wb.wait("aardio");//等待指定网址,可以使用模式匹配语法

//启动消息循环
win.loopMessage();

```

`/*DSG{{*/..../*}}*/` 这中间的部分是窗体设计器生成的代�?这里生成的实际上是一个普通的 winform 窗体.

�?web.form 是一个装饰类,可以在现有窗口对象上插入网页浏览�?并返回一个浏览器对象wb.通过浏览器对象就可以控制网页、从而实�?web 编程�?
装饰类是指的该类用于装饰被装饰的对象,以添加行为和属�? 装饰类一般并不改变对象的本质,这就好象往墙上刷涂料，无论怎么刷改变的只是外观，墙还是墙�?
这里 web.form 用来装饰 winform 对象,从一�?普通的窗口"改变�?可以浏览网页的窗�?,但窗口还是窗�?winform�?象依然可以象普通窗口那样使用�?
## web.form 构造函�?
1. 函数原型�?

   ```aardio aardio
   //创建 Web 窗体
   var wb = web.form( 窗口对象
   ,//可输入_UIFLAG_ 前缀的常量自定义外观
   ,//可输入_DLCTL_ 前缀的常量以控制下载行为
   );

   ```


   本手册中约定使用 wb 变量名表示web.form类创建的 Web 窗体对象.使用ele表示 Web 窗体中的元素对象,这也是aardio中默认约定具有特殊意义的变量�?不应将这些默认变量名用于其他目的.

2. 函数说明�?
   web.form 是一个类,其构造函数可以在现有窗口对象中插入浏览器控件�?   窗口对象可以是一�?win.form 对象,也可以是窗体上的控件,例如 custom 控件、static 控件�?
   第二个参数可以使用一个或多个\_UIFLAG\_ 前缀的常量自定义外观,多个常量之间用位或操作符( `|` ) 连接.

   可选参数如�?
   字段字段\_UIFLAG\_DIALOG禁止选中文本( 用于 web ui )\_UIFLAG\_SCROLL\_NO禁用滚动条\_UIFLAG\_NO3DBORDER禁用所有窗�?D边框\_FLAG\_NO3DOUTERBORDER禁用顶层窗口3D边框\_UIFLAG\_DISABLE\_HELP\_MENU在菜单中移除帮助菜单\_UIFLAG\_DISABLE\_SCRIPT\_INACTIVE窗口激活以前不运行网页脚本\_UIFLAG\_OPENNEWWIN在新窗口打开链接\_UIFLAG\_FLAT\_SCROLLBAR显示平面滚动条\_UIFLAG\_ACTIVATE\_CLIENTHIT\_ONLY仅在用户点击客户区时激�?非客户区指滚动条等位�?\_UIFLAG\_URL\_ENCODING\_DISABLE\_UTF8禁用UTF8发送URL\_UIFLAG\_URL\_ENCODING\_ENABLE\_UTF8使用UTF8发送URL\_UIFLAG\_ENABLE\_FORMS\_AUTOCOMPLETE允许表单自动完成\_UIFLAG\_ENABLE\_INPLACE\_NAVIGATION在点击邮件等链接时，打开相关应用程序，而不是新开窗口\_UIFLAG\_NOTHEME使用主题\_UIFLAG\_THEME禁用主题\_UIFLAG\_NOPICS禁用内容分级\_UIFLAG\_DIV\_BLOCKDEFAULT编辑模式回车输入div\_UIFLAG\_DISABLE\_EDIT\_NS\_FIXUP编辑模式禁用名字空间修正\_UIFLAG\_LOCAL\_MACHINE\_ACCESS\_CHECK防止远程网页导航到本地计算机\_UIFLAG\_DISABLE\_UNTRUSTEDPROTOCOL禁止非信任协�?包含 ms-its, ms-itss, its,mk:@msitstore
   第三个参数可使用\_DLCTL\_前缀的常量以控制下载行为,多个常量之间用位或操作符( \| ) 连接.

   可选参数如�?
   字段字段\_DLCTL\_DLIMAGES允许从服务器下载图片,如果指定了第三个参数,未指定此标志,则网页不下载任何图片.\_DLCTL\_VIDEOS允许从服务器下载视频片断,如果指定了第三个参数,未指定此标志,则网页不下载任何视频片断.\_DLCTL\_BGSOUNDS允许播放文档指定的背景声音\_DLCTL\_NO\_SCRIPTSWeb 窗体不执行任何页面脚�?指javascript�?\_DLCTL\_NO\_JAVAWeb 窗体不执行任�?Java applet\_DLCTL\_NO\_RUNACTIVEXCTLSWeb 窗体不执行文档中的任�?ActiveX 控件；\_DLCTL\_NO\_DLACTIVEXCTLSWeb 窗体不下载文档中的任�?ActiveX 控件；\_DLCTL\_DOWNLOADONLYWeb 窗体下载网页,但不显示\_DLCTL\_NO\_FRAMEDOWNLOADWeb 窗体对包含框架的页面进行语法分析但不下载任何帧， 同时忽略框架，\_DLCTL\_RESYNCHRONIZEWeb 窗体忽略缓存中的数据并向服务器请求更新\_DLCTL\_PRAGMA\_NO\_CACHE迫使请求发送给服务器并忽略代理(这里一般指服务端缓�?，即使代理指明数据是最新的也是如此.\_DLCTL\_NO\_METACHARSET隐藏文档中的 META 元素指示的字符集；\_DLCTL\_URL\_ENCODING\_DISABLE\_UTF8禁止 UTF-8 编码\_DLCTL\_URL\_ENCODING\_ENABLE\_UTF8允许 UTF-8 编码\_DLCTL\_NOFRAMES禁止框架\_DLCTL\_FORCEOFFLINEWeb 窗体工作在脱机方式\_DLCTL\_NO\_CLIENTPULLWeb 窗体不执行任何客户端�?pull 操作\_DLCTL\_SILENT组件对话框、脚本错误对话框静默模式\_DLCTL\_OFFLINEIFNOTCONNECTED如果未连接互联网，浏览器组件将以脱机方式工作
3. 调用示例�?

   ```aardio aardio
   //创建 Web 窗体
   var wb = web.form( winform.static //这是winform窗体上的一个静态文本框控件
       ,0x4/*_UIFLAG_NO3DBORDER*/ | 0x8/*_UIFLAG_SCROLL_NO*/  //禁用边框,禁用滚动�?       ,0x10/*_DLCTL_DLIMAGES*/ | 0x40000000/*_DLCTL_SILENT*/  //允许下载图片,但是禁用组件对话框、脚本错误对话框�?   );

   ```


[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/webform.md)

