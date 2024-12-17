[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 控制 Web 窗体

参�? [创建 Web 窗体](webform.html)

## 控制 Web 窗体

我们可以使用 Web 窗体提供的函数控�?Web 窗体的动作�?
本手册中约定使用 wb 变量名表�?web.form 类创建的 Web 窗体对象。使�?ele 表示 Web 窗体中的元素对象,这也�?aardio 中默认约定具有特殊意义的变量名，不应将这些默认变量名用于其他目的�?
## wb.go [\#](\#go)

1. 函数原型�?
   `wb.go(网址,自定义http请求�?目标窗口="_self")`

2. 函数说明�?
   一般我们仅需指定需要打开的目标网址就可以了,其他参数为可选参�?


   http请求头一般是以冒号分隔的键值对组成，多个键值对之间以回车换�?`\r\n` 分隔.


   例如:

   `'\r\nContent-Type: application/x-www-form-urlencoded'`

3. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   wb.go("http://www.aardio.com/")

   ```


## wb.post [\#](\#post)

1. 函数原型�?
   `wb.post( 目标网址,要提交的数据 ,自定义头='\r\nContent-Type: application/x-www-form-urlencoded',目标框架="_self")`

2. 函数说明�?
   这个函数类似 wb.go ,打开一个网址,各参数的用法类似.


   不同的是多了第二个参�?在第二个参数中可以指定要自动提交的数�?

   实际上我们在网页上看到登录、发贴之类的表单，填写好内容以后点击提交，最后浏览器都是执行一个post提交的动�?所以调用这个函数实际上省略了填写表单的过程.直接达到目的,与手工填表然后提交达到的效果是一样的.因为服务器根本不知道你在自已的电脑上做了什�?它只是从你post提交的数据来判断下一步该给你展现什么样的内�?
3. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   //打开目标网站
   wb.post("http://httpbin.org/post"
   ,"username=aardio&password=aardio&question=0&answer=&templateid=0" )

   ```


## 链接资源文件

如果将网页置于资源目�?在开发时该文件是硬盘文件，发布后根据发布选项，可能是内嵌的资源，也可以发布为硬盘文件，在 aardio 中例�?string.load 等函数都可以自动识别支持两种发布方式,无需修改代码�?
wb.go,web.post 等函数也可以自动支持 aardio 资源文件中的网页,并可支持网页中的相对路径(图片等附件的路径)�?
## wb.goBack

1. 函数原型�?
   `wb.goBack()`

2. 函数说明�?
   后退到上一次打开的网�?可以响应 [wb.CommandStateChange](event.html#CommandStateChange) 来判断是否可以后退.


## wb.goForward

1. 函数原型�?
   `wb.goForward()`

2. 函数说明�?
   返回后退之前的网�? .可以响应 [wb.CommandStateChange](event.html#CommandStateChange) 来判断是否可以后退.


## wb.goHome()

1. 函数原型�?
   `wb.goHome()`

2. 函数说明�?
   打开主页


## wb.goSearch

1. 函数原型�?
   `wb.goSearch()`

2. 函数说明�?
   打开搜索�?

## wb.refresh

1. 函数原型�?
   `wb.refresh()`

2. 函数说明�?
   刷新页面,如果服务器未更新不会重新下载，类似在浏览器中按F5的效�?

## wb.refresh2

1. 函数原型�?
   `wb.refresh2()`

2. 函数说明�?
   重新下载页面.强制刷新客户端缓�?


## wb.refresh3

1. 函数原型�?
   `wb.refresh3()`

2. 函数说明�?
   重新下载最新页�?添加Pragma:no-cache请求�?强制刷新服务器缓�?类似在浏览器中按下Ctrl+F5的效�?

## wb.stop

1. 函数原型�?
   `wb.stop()`

2. 函数说明�?
   停止当前导航


## wb.write

1. 函数原型�?
   `wb.write( 要写入的HTML代码,框架�?)`

2. 函数说明�?
   �?Web 窗体指定框架窗口写入HTML代码,框架名可省略,默认写入顶层窗口.

   该函数结束会关闭输出缓冲,每次调用wb.write都会覆盖以前的写入的内容.


## wb.document.write

1. 函数原型�?
   `wb.document.write( 要写入的HTML代码 )`

2. 函数说明�?
   该函数类�?wb.write 写入HTML到网�?区别在于不能指定框架窗口,并且在函数结束后不会关闭输出缓冲,即每次写入的内容会追加到上一次写入的内容后面,在最后一次写�?HTML 时调�?wb.write 函数可以关闭输出缓冲.

   请参�? [wb.document](getele.html#document)


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/control.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/control.md')

