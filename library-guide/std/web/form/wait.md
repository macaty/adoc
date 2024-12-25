[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 等待网页下载

参�? [创建 Web 窗体](webform.html) [获取DOM节点对象](getele.html)

## 等待网页下载

我们需要控制网页上的DOM对象,就需要等待网页下�?DOM对象成功创建,否则获取节点将会失败,网页等待是web模拟控制技术的重要组成部分,下面我们介绍 Web 窗体提供的等待下载有关的函数.

本手册中约定使用 wb 变量名表�?web.form 类创建的 Web 窗体对象.使用ele表示 Web 窗体中的元素对象,这也是aardio中默认约定具有特殊意义的变量�?不应将这些默认变量名用于其他目的.

## wb.wait [\#](\#wait)

1. 函数原型�?
   `是否成功下载 = wb.wait( 等待的网址 )`

2. 函数说明�?
   这是很重要的一个函�?在调用wb.go或wb.post打开网页以后,使用此函数可以等待目标网页完全打开.在页面完全打开以后,我们才能获取并控制网页节点对�?

   等待的网址是一个可选参�?支持 [模式查找语法](../../../builtin/string/patterns.html)


   如果不指定参�?则等待当前网页完全下载完�?

   如果打开网址时遇到错�?该函数返�?false


## wb.waitDoc [\#](\#waitDoc)

1. 函数原型�?
   `document = wb.waitDoc( 框架�?)`

2. 函数说明�?
   此函数内部循环调�?[wb.getDoc](getele.html#getDoc) ,如果发现文档对象已成功创建就立即返回,而不是等到整个网页下载完�?

   因为网络的原�?或者网站本身设计的问题,有一些网页可能很久都显示"正在下载�?.....",而实际上网页已经全部显示�?正在下载的可能是一些我们根本用不到的HTML节点.这时候这个函数就很有�?

   如果关闭 Web 窗体, wb.waitDoc 则返�?null �?
3. 调用示例


   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   //打开目标网站
   wb.go("http://www.aardio.com/")
   //显示窗体
   winform.show(true)

   doc = wb.waitDoc();

   ```


## wb.waitEle [\#](\#waitEle)

1. 函数原型�?
   `是否成功下载 = wb.waitEle( HTML节点的ID名name, 框架�?)`

2. 函数说明�?
   此函数内部循环调�?[wb.getEle](getele.html#getEle) ,如果发现该节点已成功创建就立即返�?而不是等到整个网页下载完�?


   因为网络的原�?或者网站本身设计的问题,有一些网页可能很久都显示"正在下载�?.....",而实际上网页已经全部显示�?正在下载的可能是一些我们根本用不到的HTML节点.这时候这个函数就很有�?

   如果关闭 Web 窗体,wb.waitEle则返回null,否则该函数一直尝试获取指定的节点,一旦获取成功就返回该节�?

3. 调用示例


   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   //打开目标网站
   wb.go("http://www.aardio.com/")
   //显示窗体
   winform.show(true)
   ele = wb.waitEle( "__VIEWSTATE" );//等待指定网址,可以使用模式匹配语法

   import console;
   console.log( ele.outerHTML )

   ```


## wb.waitClose [\#](\#waitClose)

1. 函数原型�?
   wb.waitClose()

2. 函数说明�?
   等待 Web 窗体关闭.


[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/wait.md)

