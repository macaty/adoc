[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# 获取DOM节点对象

参�? [创建 Web 窗体](webform.html)

## DOM简�?
网页上是一个个的HTML节点表示�?DOM 节点对象,节点象一颗树,所有节点的根是 wb.document 对象,一个节点可以包含另外的一个或多个节点,�?Web 窗体�?我们通过获取节点对象就可以读写网页上任意节点的数据、并控制这些节点的行为，从而实现自动化的目的�?
本手册中约定使用 wb 变量名表�?web.form 类创建的 Web 窗体对象.使用 ele 表示 Web 窗体中的元素对象,这也�?aardio 中默认约定具有特殊意义的变量�?不应将这些默认变量名用于其他目的�?
在获取节点对象以�?我们必须调用 [wb.go](control.html#go) 打开网页,并调�?[wb.wait](wait.html#wait) 等待网页下载完毕并完全打开�?
## wb.document

wb.document是网页上所有节点对象的根节�?这是一个com对象,可以使用 com.DumpTypeInfo �?console.dump 函数列出该对象的成员,请参考HTML DOM文档以了解document的成员�?
```aardio aardio
import console;
console.dump( wb.document );

```

## wb.getDoc

1. 函数原型�?
   `doc = wb.getDoc( 框架�?)`

2. 函数说明�?
   获取指定框架窗口的document对象,框架名可省略.


   如果无参�?该函数返�?wb.document

   如果页面未成功创建文档对�?该函数返回null,调用该函数以前必须调�?[wb.wait()](wait.html#wait) 等待网页下载完毕.


   而使�?[wb.waitDoc()](wait.html#waitDoc) 则实现等待该节点下载并返回该节点的功�?而无须等待整个网页下载完.


## wb.body

wb.body是网页上所有可见元素的根节�?这是一个element对象,可以使用com.DumpTypeInfo函数列出该对象的成员

```aardio aardio
import console;
console.dump( wb.body );
console.pause();

```

## wb.getEle

1. 函数原型�?
   `ele = wb.getEle( HTML节点的ID名name, 框架�?)`

2. 函数说明�?
   该函数查找并返回页面上的 element 节点对象,


   该对象同样是一�?COM 对象,可以使用 com.DumpTypeInfo �?console.dump 函数列出该对象的成员.

   可以通过第二个参数指定框架窗口，该参数可以省略�?
   调用 wb.getEle 之前必须调用 [wb.wait()](wait.html#wait) 等待网页下载完毕.


   而使�?[wb.waitEle()](wait.html#waitEle) 则实现等待该节点下载并返回该节点的功�?而无须等待整个网页下载完.


## wb.fromPoint

1. 函数原型�?
   `ele = wb.fromPoint( x坐标,y坐标, 框架�?)`

2. 函数说明�?
   自指定的窗口坐标获取节点,

   可以通过第三个参数指定框架窗�?该参数可以省�?


## wb.getEles

1. 函数原型�?
   `tele = wb.getEles( HTML节点的name属�? 框架�?)`

2. 函数说明�?
   该函数返回网页上所有name属性相同的同名节点.返回值为一个com数组.注意com数组使用()括号读取成员而不是使用索引操作符 `[]`

   可以通过第二个参数指定框架窗�?该参数可以省�?

3. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   tele = wb.getEles( HTML节点的name属�? 框架�?)
   tele(1).setAttribute("属性名�?, "修改第一个节点属性�?)

   ```


## wb.eachAll

1. 函数原型�?

   ```aardio aardio
   for(k,ele in wb.eachAll( HTML标记,框加�? ){

   }

   ```

2. 函数说明�?
   wb.eachAll创建一个用于for...in语句的迭代器,用以遍历页面上指定的节点.

   参数一指定 HTML 标记 可以通过第二个参数指定框架窗�?该参数可以省�?

3. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   import console;
   for(k,ele in wb.eachAll( "a" ) ){

       console.log( ele.innerHTML ) //输出页面上所有的超链接包含的HTML
   }

   ```


## wb.eachLinks

1. 函数原型�?

   ```aardio aardio
   for(k,ele in wb.eachLinks( 框架�? ){

   }

   ```

2. 函数说明�?
   此函数类�?wb.eachAll ,无需指定HTML标记,默认列出页面上所有的超链�?

3. 调用示例�?

   ```aardio aardio
   //....省略创建 Web 窗体的代�?
   import console;
   for(k,ele in wb.eachLinks() ){

       console.log( ele.innerHTML ) //输出页面上所有的超链接包含的HTML
   }

   ```


[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/getele.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/std/web/form/getele.md')

