[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# winex �?
winex 库主要扩�?win 库的功能，并提供管理外部进程窗口的函数与窗口自动化有关的功能�?
## winex.match [\#](\#match)

1. 函数原型�?
   `是否匹配 = winex.match(窗口句柄,文本,类名,ID,超时)`

2. 函数说明�?
   所有参数可�?

   检测给定窗口句柄的窗口属性，与给定的参数进行比较，如果相符返回真(true)，否则返回假(false) �?
   使用模糊匹配比较类名、标题，支持 [模式语法](../../builtin/string/patterns.html) �?
   可选指定一个以毫秒为单位的超时值�?
   winex 库中查找窗口的函数多是调用此函数对窗口进行匹配�?

## winex.find [\#](\#find)

1. 函数原型�?
   `hwnd,线程ID,进程ID = winex.find( 类名,标题,进程ID,线程ID )`

   注意：本文档�?hwnd 用于表示窗口句柄的变量名�?
2. 函数说明�?
   按给定的参数查找指定的窗口，所有参数都是可选参数�?

   winex.find使用模糊匹配来查找类名、标题，支持 [模式语法](../../builtin/string/patterns.html) �?
   如果需要简单匹配，请使�?[win.find](../win/_.html#find)

3. 调用示例�?

   ```aardio aardio
   import winex;
   import process;
   import console;

   //运行目标程序
   var prcs = process( "请指定文件名.exe"  )

   //查找窗口
   var hwnd = winex.find("请指定类�? , ,prcs.id /*根据进程ID也可以找到窗�?/ );
   console.logPause("找到句柄�?, hwnd )

   ```


## winex.findEx [\#](\#findEx)

1. 函数原型�?
   `hwnd = winex.findEx( 父窗口句�?返回第几个匹配句�?类名模式�?,标题模式�? 控件ID )`

2. 函数说明�?
   按给定的参数查找指定的窗口，除父窗口句柄以外所有参数都是可选参数�?
   winex.findEx使用模糊匹配来查找类名、标题，支持 [模式查找语法](../../builtin/string/patterns.html) �?
   如果需要简单匹配，请使�?[win.findEx](../win/_.html#findEx)

3. 调用示例�?

   ```aardio aardio
   import process;
   import winex;

   //运行程序
   process.execute("请指定文�?exe")

   //查找
   var hwnd = win.find("请指定类�?);//查找父窗�?   var hedit = winex.findEx(hwnd,1,"Edit" ); //查找第一个类名为Edit的子窗口

   //输出结果
   console.logPause("找到目标程序中的文本框句柄：", hedit )


   ```


## winex.findExists [\#](\#findExists)

1. 函数原型�?

   ```aardio aardio
   窗口句柄,控件句柄,线程ID,进程ID = winex.findExists( 父窗口标�?控件文本 )

   窗口句柄,控件句柄,线程ID,进程ID = winex.findExists(
                   父窗口标�?
                   控件文本,
                   父窗口类�?
                   控件类名,
                   控件ID
               )

   ```

2. 函数说明�?
   所有参数都是可选参�?但一般应指定父窗口标题与控件文本.


   这个函数基本是结合了winex.find与winex.findEx的功�?首先查找符合条件的父窗口,再查找它是否包含符合条件的控件窗�?您可以打开winex库查看此函数的源代码.

   winex.findExists同样支持使用模糊匹配来查找类名、标题，支持 [模式查找语法](../../builtin/string/patterns.html) �?
   这个函数是非常有用的一个函�?

3. 调用示例�?

   ```aardio aardio
   import winex;
   import process
   import console;

   //运行目标程序
   process.execute( "notepad.exe")

   //查找包含指定标题,并包含类名为"Edit"控件的窗�?
   窗口句柄,控件句柄,线程ID,进程ID = winex.findExists("<标题1>|<标题2>","", ,"Edit")

   //显示结果
   console.log( 窗口句柄,控件句柄,线程ID,进程ID  )

   //关闭窗口
   win.close(窗口句柄)

   console.pause(true);

   ```


## winex.findActivate [\#](\#findActivate)

```aardio aardio
1. 函数原型�?
窗口句柄,控件句柄,线程ID,进程ID = winex.findActivate( 父窗口标�?控件文本 )

窗口句柄,控件句柄,线程ID,进程ID = winex.findActivate(
                父窗口标�?
                控件文本,
                父窗口类�?
                控件类名,
                控件ID
            )

```

1. 函数说明�?
   此函数用法与winex.findExists完全相同,内部直接调用winex.findExists.

   不同的是:winex.findActivate会在找到窗口后激活窗口使之成为前台窗�?


## winex.wait [\#](\#wait)

1. 函数原型�?

   ```aardio aardio
   窗口句柄,控件句柄,线程ID,进程ID = winex.wait( 父窗口标�?控件文本 )

   窗口句柄,控件句柄,线程ID,进程ID = winex.wait(
                   父窗口标�?
                   控件文本,
                   父窗口类�?
                   控件类名,
                   控件ID
               )

   ```

2. 函数说明�?
   所有参数都是可选参�?但一般应指定父窗口标题与控件文本.


   这个函数内部调用winex.findExists,所以参数用法与winex.findExists完全一�?请参考此函数说明.


   winex.wait同样支持使用模糊匹配来查找类名、标题，支持 [模式查找语法](../../builtin/string/patterns.html) �?
   该函数指定一些可选的参数,等待指定的窗口创�?然后返回.


   可使�?winex.waitTimeout 指定超时�?以毫秒为单位),如果此属性为null空�?表示永不超时.


   可使�?winex.waitDelay 指定检测间�?以毫秒为单位),默认�?00毫秒.

   该函数如果超时并失败则返回空�?


## winex.waitClose [\#](\#waitClose)

1. 函数原型�?

   ```aardio aardio
   是否成功 = winex.waitClose( 窗口句柄 )

   是否成功 = winex.waitClose(
                   父窗口标�?
                   控件文本,
                   父窗口类�?
                   控件类名,
                   控件ID
               )

   ```

2. 函数说明�?
   此函数用法与winex.wait类似,请参考winex.wait说明.


   不同的是,winex.waitClose可以指定一个窗口句柄作为参�?


   并且 winex.waitClose只有一个返回�?表示是否成功.

   该函数指定一些可选的参数,等待指定的窗口关�?然后返回.


   可使�?winex.waitTimeout 指定超时�?以毫秒为单位),如果此属性为null空�?表示永不超时.


   可使�?winex.waitDelay 指定检测间�?以毫秒为单位),默认�?00毫秒.

   如果超时返回false,成功则返回true;


## winex.waitActive [\#](\#waitActive)

1. 函数原型�?

   ```aardio aardio
   窗口句柄 = winex.waitActive( 窗口句柄 )

   窗口句柄,控件句柄,线程ID,进程ID = winex.waitActive(
                   父窗口标�?
                   控件文本,
                   父窗口类�?
                   控件类名,
                   控件ID
               )

   ```

2. 函数说明�?
   此函数用法与winex.waitClose类似,请参考winex.waitClose说明.

   winex.waitActive返回激活窗口的句柄.如果使用了winex.wait相同的参�?则返回与winex.wait相同的返回�?窗口句柄,控件句柄,线程ID,进程ID)

   该函数指定一些可选的参数,等待指定的窗口激�?然后返回. 可使�?winex.waitTimeout 指定超时�?以毫秒为单位),如果此属性为null空�?表示永不超时. 可使�?winex.waitDelay 指定检测间�?以毫秒为单位),默认�?00毫秒.

   如果超时返回空�?否则返回激活窗口的句柄.

   注意:此函数内部调�?win.getForeground() 检测激活窗口，而非 win.getActive() 。win.getActive() 仅能获取当前线程的激活窗�?而非系统激活窗�?通常会因为名称而导致误�?


## 枚举窗口 [\#](\#enum)

请参考： [枚举与遍历](../../../language-reference/function/enum-and-each.html)

1. 函数原型�?
   `winex.enum( 回调函数,父窗口句�?= 桌面窗口,要查找的类名,要查找的标题,要查找的控件ID )`

2. 函数说明�?
   在指定的父窗口枚举所有子窗口、除回调函数以外，所有参数为可选参数。类名与标题支持 [模式语法](../../builtin/string/patterns.html) �?
   每查找到一个窗口就调用第一个参数指定的回调函数。回调函数按下面的格式定义：


   ```aardio aardio
   function( 找到的窗口句�?窗口嵌套深度 ){
   //返回false停止枚举
   }

   ```

3. 调用示例�?

   ```aardio aardio
   import winex;
   import console;

   winex.enum(
       function(hwnd,depth){

       console.log( depth/*深度*/,hwnd/*窗口*/,win.getText(hwnd)/*标题*/ )
       /*return false*/
   } )

   ```


## 枚举顶层窗口 [\#](\#enumTop)

请参考： [枚举与遍历](../../../language-reference/function/enum-and-each.html)

1. 函数原型�?
   `winex.enumTop( 回调函数 )`

2. 函数说明�?
   枚举所有桌面顶层窗口�?

   每查找到一个窗口就调用第一个参数指定的回调函数。回调函数按下面的格式定义：


   ```aardio aardio
   function( 找到的窗口句�?){
   //返回false停止枚举
   }

   ```


   winex.enumTop的实现较简单，执行速度也很快，如果仅仅是需要例出顶层窗口的句柄，不需要其他的功能，应优先选用此函数�?
3. 调用示例�?

   ```aardio aardio
   import winex;
   import console;

   winex.enumTop(
       function(hwnd){
           console.log(hwnd)
       }
   )

   console.pause(true);

   ```


## 遍历窗口 [\#](\#each)

请参考： [枚举与遍历](../../../language-reference/function/enum-and-each.html)

1. 函数原型�?
   `winex.each( 要查找的类名,要查找的标题,父窗口句�?= 桌面窗口 )`

2. 函数说明�?
   父窗口句柄为可选参数，默认为桌面窗口。类名和标题都支�?[模式查找语法](../../builtin/string/patterns.html) �?
   winex.each 创建一个可用于 [for in](../../../language-reference/statements/looping.html#for-in) 语句的迭代器函数，用于广度遍历同一子级的子窗口�?

## winex.fromPoint [\#](\#fromPoint)

1. 函数原型�?
   `hwnd = winex.fromPoint( 屏幕坐标x,屏幕坐标y )`

2. 函数说明�?
   从指定的屏幕坐标获取窗口，如果窗口拥有子窗口则递归获取子窗口直到叶级窗�?

## winex.fromPointReal

1. 函数原型�?
   `hwnd = winex.fromPointReal( 屏幕坐标x,屏幕坐标y )`

2. 函数说明�?
   此函数首先调用winex.fromPoint，然后调用winex.fromClientPointReal,可穿透groupbox控件获取内部控件窗口


## winex.fromClientPoint [\#](\#fromClientPoint)

1. 函数原型�?
   `hwnd = winex.fromClientPoint(父窗口句�? 客户坐标x,客户坐标y,un=_CWP_SKIPINVISIBLE )`

2. 函数说明�?
   在指定的父窗口获取、从指定的屏幕坐标获取该位置子窗口句�?不能获取子窗口的子窗�?�?
   un为可选参数，默认为\_CWP\_SKIPINVISIBLE，其他可选参数：
   参数说明0x0000/\*\_CWP\_ALL\*/测试所有窗�?x0001/\*\_CWP\_SKIPINVISIBLE\*/忽略不可见窗�?x0002/\*\_CWP\_SKIPDISABLED\*/忽略已屏蔽的窗口0x0004/\*\_CWP\_SKIPTRANSPARENT\* /忽略透明窗口

## winex.fromClientPointReal [\#](\#fromClientPointReal)

1. 函数原型�?
   `hwnd = winex.fromClientPointReal(父窗口句�? 屏幕坐标x,屏幕坐标y,un=_CWP_SKIPINVISIBLE )`

2. 函数说明�?
   在指定的父窗口获取、从指定的屏幕坐标获取该位置子窗口句�?不能获取子窗口的子窗�?


   可穿透groupbox控件获取内部控件窗口.


## winex.getFocus [\#](\#getFocus)

1. 函数原型�?
   `hfocus = winex.getFocus( hwnd )`

2. 函数说明�?
   返回指定窗口输入焦点所在的控件句柄，如果参数hwnd是一个控件，则直接返回该控件的句柄�?

   此函数支持获取外部线程的输入焦点，�?[win.getFocus](../win/_.html#getFocus) 只能支持当前线程的窗�?

## winex.click [\#](\#click)

1. 函数原型�?
   `hwnd = winex.click( 窗口句柄,命令ID )`

2. 函数说明�?
   窗口上的菜单、按钮等都会有一个控件ID，可以使用winex.click函数直接向包含该控件的主窗口发送该ID的命令消息，达到后台模拟点击控件的效果�?
   可以使用附带的工具：winspy查看控件ID，使用查看资源文件的软件查看菜单项的ID�?

## winex.findMenu

1. 函数原型�?
   `hwnd = winex.findMenu( 窗口句柄,菜单标题 | 菜单ID,...... )`

2. 函数说明�?
   第一个参数为目标窗口句柄�?

   自第二个参数开始可选添加任意多个参数，可用字符串表示菜单项标题，或用数值表示菜单序号�?

   菜单标题支持 [模式查找语法](../../builtin/string/patterns.html) ，菜单序号自1开�?第一个子菜单序号�?�?
3. 调用示例�?

   ```aardio aardio
   //导入winex�?   import winex;

   //查找
   var hwnd = win.find("指定窗口类名");//查找父窗�?
   //查找指定的菜�?"文件"菜单下的子菜�?另存�?)
   hmenu,menuid = winex.findMenu(hwnd ,"文件","另存�?  );

   //前置窗口
   win.setForeground(hwnd)

   //点击菜单�?   winex.click( hwnd,menuid)

   ```


## winex.attach [\#](\#attach)

1. 函数原型�?
   `是否成功 = winex.attach( 窗口句柄,是否附加=true )`

2. 函数说明�?
   绑定当前线程到外部窗口所属线程并共享输入处理机制�?
   参数应指定一个非当前线程的窗�?如果第二个参数为�?可省略参�?默认为真)�?
   通常，系统内的每个线程都有自己的输入队列。winex.attach 允许当前线程与目标窗口共享输入队列。连接了线程后，输入焦点、窗口激活、鼠标捕获、键盘状态以及输入队列状态都会进入共享状�?返回�?Long，非零表示成功，零表示失败�?
   调用 winex.attach 以后,可以在附加的目标窗口使用 win.getFocus() win.setFocus() 等函�?也可以方便地使用winex.key winex.mouse等函数库提供的后台模拟函�?

   附加与解除应配对使用,例如调用 winex.attach(hwnd)附加成功以后,在不再需要附加时应调用winex.attach(hwnd,false)解除.


## winex.attachThread [\#](\#attachThread)

1. 函数原型�?
   `是否成功 = winex.attachThread( 目标线程ID,是否附加=true )`

2. 函数说明�?
   绑定当前线程到外部线程并共享输入处理机制�?
   此函数与 winex.attach 的功能一样�?
   区别是第一个参数需指定线程ID，而不是窗口句柄�?
   其他参�?[winex.attach](#attach) 函数�?

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/std/winex/winex.md)

