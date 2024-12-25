[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 事件接口

参�? [创建 Web 窗体](webform.html)

## 事件接口

Web 窗体实现�?web 事件接口. �?Web 窗体产生事件�?例如下载完开�?下载完成�?，会查询 Web 窗体对象是否定义了相关的事件函数，如果有相应的事件函数，则自动调用该函数�?
例如，对于一�?Web 窗体对象 wb , 在用户在网页上右键点击网页时,如果自定�?wb.showMenu 事件函数，则调用该函数显示自定义的菜单，否则显示默认的菜单�?
每一个事件函数都是一个触发器函数、一个回调函数。在 Web 窗体产生事件时通过回调触发事件函数.

本手册中约定使用 wb 变量名表�?web.form 类创建的 Web 窗体对象.使用 ele 表示 Web 窗体中的元素对象,这也�?aardio 中默认约定具有特殊意义的变量�?不应将这些默认变量名用于其他目的.

## wb.showMenu

1. 函数原型�?

   ```aardio aardio
   wb.showMenu = function(x,y,id,ele){
   return 是否显示默认菜单;
   }

   ```

2. 函数说明�?
   当用户右键点击网页上的元素时,触发此事�?如果未定义些事件函数,弹出默认右键菜单.

   x,y 表示右键点击的坐�?�?ele 表示发生事件的节点对�? id 表示节点的类�?有以下�?
   id说明`0/*_CONTEXT_MENU_DEFAULT */`默认右键菜单`1/*_CONTEXT_MENU_IMAGE*/`图片右键菜单`2/*_CONTEXT_MENU_CONTROL*/`控件右键菜单`3/*ONTEXT_MENU_TABLE*/`表格`4/*_CONTEXT_MENU_TEXTSELECT*/`文本选区右键菜单`5/*_CONTEXT_MENU_ANCHOR*/`锚点,超链接`6/*_CONTEXT_MENU_UNKNOWN*/`未知`10/*_CONTEXT_MENU_VSCROLL*/`垂直滚动条`11/*_CONTEXT_MENU_VSCROLL*/`水平滚动�?3. 调用示例�?

   ```aardio aardio
   wb.showMenu=function(x,y,id,ele){

     if( id == 4/*_CONTEXT_MENU_TEXTSELECT */ )
        return true;//如果用户显示的是文本,显示默认菜单

     //自定义弹出菜�?     popmenu = win.ui.popmenu(winform);
        popmenu.add('显示节点内容',function(id){
        win.msgbox( ele.innerHTML )

     });

     popmenu.popup(x,y,true)

     return false; //禁用默认菜单
   }

   ```


## wb.showMsg

1. 函数原型�?

   ```aardio aardio
   wb.showMsg=function( 提示信息, 对话框标�?){

     return 是否显示对话�?
   }

   ```

2. 函数说明�?
   该事件在网页弹出对话框以前触�?这里指的对话框指网页脚本创建的对话框,例如javascript中的alert函数创建的对话框,函数有两个参数可以获取对话框的标�?而通过返回值可以控制对话框是否弹出.

   有些javascript脚本通过对话框获取用户的输入,这时�?我们可以使用 wb.doScript("要执行的javascript脚本") 以执行网页脚本来绕过对话框实现目的功�?

   还有一种方�?就是让对话框弹出�?再自动点击指定的按钮,并关闭对话框.我们知道,对话框弹出以�?程序就一直等待用户的操作,不会执行对话框后面的代码,因此:我们需要在对话框弹出之前创建一个后台线�?来关闭弹出的对话�?请看下面的示�?

3. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   wb.showMsg = function(text/*信息*/,caption/*标题*/){

     closeDlg_t = function(title) {
           import winex;
           var hwnd,hctr =   winex.waitActive(title, ,"#32770","Button");
           winex.click(hctr);
     }
     thread.create(closeDlg_t,caption/*传递参数给线程*/ )
     return true; /*返回false则不显示对话�?/
   }

   //打开目标网站
   wb.write("<script>alert('你好�?)</script>"

   ```


## wb.NewWindow2

1. 函数原型�?

   ```aardio aardio
   wb.NewWindow2=function( ppDisp, Cancel) {

     /*创建代理窗口捕获网址并在当前窗口打开*/
     return owner.openproxy

     /*第二个返回值如果为真，则取消新窗口*/
     return ppDisp, true;

     /*新建�?Web 窗体，并将application作为返回值，则在该web窗口中打开*/
     return ppDisp, Cancel
   }

   ```

2. 函数说明�?
   弹出新窗口以前触�?有两个输出参�?ppDisp, Cancel


   - ppDisp如果返回其他 Web 窗体�?application成员,则在�?Web 窗体中打开新窗�?

   - Cancel 返回值指�?Web 窗体是否取消该弹出窗�?例如:return ppDisp,true将会取消弹出窗口.


如果希望在当前窗口中打开链接,则要采取一点技巧，使用一个代理窗口打开网页，在代理窗口中获取网址以后再停止导航并使用当前窗口打开网页.示例如下:

3. 调用示例�?

   ```aardio aardio
   wb.NewWindow2 = function( ppDisp, Cancel) {

     return owner.openproxy /*创建代理窗口捕获网址并在当前窗口打开*/
   }

   ```


## wb.NewWindow3

1. 函数原型�?

   ```aardio aardio
   wb.NewWindow3=function(ppDisp, Cancel,dwFlags,bstrUrlContext, bstrUrl ) {

     console.log(  ppDisp, Cancel,dwFlags,bstrUrlContext, bstrUrl  )
   }

   ```

2. 函数说明�?

   win xp sp2以上版本的win操作系统支持此事�?ppDisp, Cancel是输出参�?使用方法与wb.NewWindow2类似.


   而wb.NewWindow3多了一些参�?其中bstrUrlContext指为打开新窗口的源网页url,而bstrUrl为即将打开的目标url,dwFlags可选值如�?   dwFlags说明\_NWMF\_UNLOADING = 0x00000001,在原网页关闭时弹出的窗口\_NWMF\_SHOWHELP = 0x00000010在脚本中调用window showHelp 显示的窗口\_NWMF\_HTMLDIALOG = 0x00000020显示HTML对话框\_NWMF\_USERREQUESTED = 0x00000080用户请求打开的新窗口\_NWMF\_FORCEWINDOW = 0x00010000弹出窗口

## wb.CommandStateChange

1. 函数原型�?

   ```aardio aardio
   wb.CommandStateChange = function(cmd,enable) {

   }

   ```

2. 函数说明�?
   当命令的激活状态改变时触发。它表明何时激活或关闭Back和Forward菜单项或按钮.


   enable参数说明指定的命令是否可�?而cmd可选参数如�?
   cmd说明\_CSC\_UPDATECOMMANDS是否可以刷新控制按钮、工具栏\_CSC\_NAVIGATEFORWARD前进命令是否可用\_CSC\_NAVIGATEBACK后退命令是否可用

## wb.DownloadBegin

1. 函数原型�?

   ```aardio aardio
   wb.DownloadBegin = function(){

   }

   ```

2. 函数说明�?
   一个下载开始时触发此事�?刷新也可触发此事�?


## wb.DownloadComplete

1. 函数原型�?

   ```aardio aardio
   wb.DownloadComplete = function(){

   }

   ```

2. 函数说明�?
   一个下载完成时触发此事�?刷新也可触发此事�?


## wb.BeforeNavigate2

1. 函数原型�?

   ```aardio aardio
   wb.BeforeNavigate2 = function( pDisp, url
   , Flags, TargetFrameName, PostData, Headers, Cancel ) {

     eturn   url, Flags, TargetFrameName, PostData, Headers,Cancel;
   }

   ```

2. 函数说明�?
   导航(打开网址)以前触发此事�?刷新不触�?
   参数说明�?

   - pDisp Web 窗体对象

   - url 要打开的网址

   - Flags 标志�?
   - TargetFrameName 目标�?
   - PostData 提交的表单数�?
   - Headers HTTP请求�?
   - Cancel 是否取消导航

除第一个参数pDisp以外,其他参数都是输出参数.返回值要按下面的顺序:

return url, Flags, TargetFrameName, PostData, Headers,Cancel;

不需要返回值的输出参数可以省略或传递null�?例如:

```aardio aardio
return   null, , , , ,true;

```

## wb.NavigateComplete2

1. 函数原型�?

   ```aardio aardio
   wb.NavigateComplete2 = function(pDisp, url){

   }

   ```

2. 函数说明�?
   每次导航完成触发此函�?刷新不触�?


   pDisp为浏览器对象,url为导航网址.


## wb.NavigateComplete

1. 函数原型�?

   ```aardio aardio
   wb.NavigateComplete = function(pDisp, url){

   }

   ```

2. 函数说明�?
   每次导航完成触发此函�?刷新不触�?


   pDisp为浏览器对象,url为导航网址.


## wb.NavigateError

1. 函数原型�?

   ```aardio aardio
   wb.NavigateError=function(pDisp,url,target,statusCode,cancel){

     return url,target,statusCode,cancel
   }

   ```

2. 函数说明�?
   导航出错时触发此函数,参数说明:


   - pDisp 浏览器对�?

   - url 出错的网址.

   - target 打开该网址的窗口名�?
   - statusCode 错误代码

   - cancel 这是一个输出参�?指示是否取消导航到默认的错误页面.


输出参数返回顺序�?

```aardio aardio
return url,target,statusCode,cancel

```

## wb.FileDownload

1. 函数原型�?

   ```aardio aardio
   wb.FileDownload=function(activeDocument, cancel){

     return cancel;
   }

   ```

2. 函数说明�?
   此函数在下载以前触发,有两个参�?


   activeDocument表示打开的目标文�?- 是不是可直接显示在窗口的活动文档.


   一般普通网页activeDocument为true,而需要弹出下载文件对话框时activeDocument参数的值为false.

3. 调用示例�?

   ```aardio aardio
   wb.FileDownload=function(activeDocument, cancel){
     if( !activeDocument ) return true; //禁止弹出下载文件对话�?   }

   ```


   注意这个事件并不提供下载文件的地址，可以在translate,NavigateError等事件中提前获取下载地址


## wb.translate

1. 函数原型�?

   ```aardio aardio
   wb.translate=function( url ) {
     return url;
   }

   ```

2. 函数说明�?
   网页解析 URL 时触发此事件,例如点击链接后，下载文件、弹出窗口以前会触发此事件，可在返回值中替换并指定新的网址�?

## wb.TitleChange

1. 函数原型�?

   ```aardio aardio
   wb.TitleChange=function( 网页标题 ) {

   }

   ```

2. 函数说明�?
   网页标题改变时触发此事件,默认的网页标题并不显示在窗口标题栏上.


## wb.WindowClosing

1. 函数原型�?

   ```aardio aardio
   wb.WindowClosing = function( IsChildWindow, Cancel ) {
   return true ; //返回真阻止窗口关�?   }

   ```

2. 函数说明�?
   在网页脚本中调用 window.close() 函数关闭网页窗口时触发此函数,在函数中返回true阻止窗口关闭.


   如果参数 IsChildWindow 为真,该窗口为网页脚本创建的子窗口.


[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/event.md)

