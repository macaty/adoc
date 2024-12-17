[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# web.mshtml 库模块帮助文�?
## web 成员列表

### web.mshtml

MSHTML（htmlfile）支持库

### web.mshtml()

创建 HTML文档对象

[返回对象:mshtmObject](#mshtmObject)

### web.mshtml(doc)

创建HTML文档对象

可选指定一个document对象

### web.mshtml(wb,框架�?

创建HTML文档对象

可选指定一个wb窗体,以及框架�?
## mshtmObject 成员列表

### mshtmObject.body

网页 body 元素

[返回对象:eleObject](#eleObject)

### mshtmObject.doScript

```aardio aardio
var js = /**
    alert("Javascript!");
**/
mshtmObject.doScript(js, )

```

### mshtmObject.document

文档对象

document.

### mshtmObject.documentMode

返回网页当前兼容模模式版本号,默认值为7,

可能的值为6,7,8,9,11等等,5为网页上没有写DOCTYPE导致的怪异模式,

可在页面中通过X-UA-Compatible设置兼容模式,

也可用web.form.emulation 函数改变当前进程的默认兼容模�?

### mshtmObject.eachAll("DIV",父节�?

```aardio aardio
//创建迭代�?迭代页面所有输入控�?例：
for i,ele in mshtmObject.eachAll("DIV" ,mshtmObject.getEle("id") ) {

}

```

```aardio aardio
//创建迭代�?迭代页面所有输入控�?例：
for i,ele in mshtmObject.eachAll("DIV" ,mshtmObject.getEle("id") ) {

}

```

### mshtmObject.eachAll("input")

```aardio aardio
//创建迭代�?迭代页面所有输入控�?例：
for i,ele in mshtmObject.eachAll("input") {

}

```

```aardio aardio
//创建迭代�?迭代页面所有输入控�?例：
for i,ele in mshtmObject.eachAll("input") {

}

```

### mshtmObject.eachAll("input","框架�?)

```aardio aardio
//创建迭代�?迭代页面所有输入控�?例：
for i,ele in mshtmObject.eachAll("input","框架�?) {

}

```

```aardio aardio
//创建迭代�?迭代页面所有输入控�?例：
for i,ele in mshtmObject.eachAll("input","框架�?) {

}

```

### mshtmObject.eachAll()

```aardio aardio
//创建迭代�?迭代页面所有节�?例：
for i,ele in mshtmObject.eachAll() {

}

[返回对象:eleObject](#eleObject)

```

```aardio aardio
//创建迭代�?迭代页面所有节�?例：
for i,ele in mshtmObject.eachAll() {

}

[返回对象:eleObject](#eleObject)

```

### mshtmObject.eachFrames("框架�?)

```aardio aardio
//创建迭代�?迭代页面所有框架窗�?例：
for i,ele in mshtmObject.eachFrames() {

}

```

### mshtmObject.eachLinks()

[返回对象:eleObject](#eleObject)

### mshtmObject.eachLinks(父节�?

```aardio aardio
//创建迭代�?迭代页面所有超链接,例：
for i,ele in mshtmObject.eachLinks(/*父节点或框架�?/) {

}

```

```aardio aardio
//创建迭代�?迭代页面所有超链接,例：
for i,ele in mshtmObject.eachLinks(/*父节点或框架�?/) {

}

```

### mshtmObject.eval

运行js代码

### mshtmObject.eval("JS代码")

返回表达式的�?
### mshtmObject.exec("字符串参�?)

执行命令

参数@2为传入参�?可省�?
参数@3指定是否显示交互界面,布尔�?可省�?
### mshtmObject.execEle(ele,"字符串参�?)

执行命令

参数@2为传入参�?可省�?
参数@3指定是否显示交互界面,布尔�?可省�?
### mshtmObject.execWb( \_OLECMDID , ,2 )

执行命令,

参数@2为传入参�?可省�?

参数@3指定UI交互选项:

1/\*\_OLECMDEXECOPT\_PROMPTUSER\*/为显示界�?

2/\*\_OLECMDEXECOPT\_DONTPROMPTUSER\*/为不显示界面

### mshtmObject.getDoc()

```aardio aardio
document.

```

### mshtmObject.getDoc(框架�?

获取文档对象

参数可以是框架名,ID,基于0的索�?或者frame节点

### mshtmObject.getEle("字符串参�?)

返回一个节点对象或框架内子节点对象

### mshtmObject.getEle("字符串参�?,"框架名字")

返回一个节点对象或框架内子节点对象

### mshtmObject.getEle()

[返回对象:eleObject](#eleObject)

### mshtmObject.getEles("字符串参�?)

返回同名的所有节�?例如

ele = wb.getEles("节点名字");

ele(1).setAttribute("属性名�?, "修改第一个节点属性�?);

### mshtmObject.getEles("字符串参�?,"框架名字")

返回同名的所有节�?例如

ele = wb.getEles("节点名字");

ele(1).setAttribute("属性名�?, "修改第一个节点属性�?);

### mshtmObject.getEles()

[返回对象:webFormElesObject](#webFormElesObject)

### mshtmObject.getElesByTag("head")

返回指定标记的所有节�?
### mshtmObject.getElesByTag("head","框架名字")

返回指定标记的所有节�?
### mshtmObject.getElesByTag()

[返回对象:webFormElesObject](#webFormElesObject)

### mshtmObject.getScript()

[返回对象:jsGlobalObject](#jsGlobalObject)

### mshtmObject.getScript(框架�?

网页脚本对象

### mshtmObject.go("字符串参�?)

打开网址或本地路�?
注意驱动器根目录要以反斜杠结�?
### mshtmObject.go("字符串参�?,"自定义http�?)

打开网址

### mshtmObject.go("字符串参�?,"自定义http�?,"目标框架")

打开网址

### mshtmObject.head

网页 head 元素

[返回对象:eleObject](#eleObject)

### mshtmObject.html

```aardio aardio
mshtmObject.html = /**
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
</head>
<body>
    <div></div>
</body>
</html>
**/

```

### mshtmObject.jQuery("字符串参�?)

jQuery选择�?并可自动载入jQuery�?
n首次调用按需加载jQuery v1.10:

"/res/js/jQuery/jQuery.min.js"

失败则通过网络CDN服务器下载jquery-1.9.0.min.js

注意 jQuery v1.6.3 以上 ajax 函数才会支持 res 协议访问 EXE 资源文件

IE11 内核默认已阻�?ajax 访问本地文件,

改用 wsock.tcp.simpleHttpServer/asynHttpServer 访问本地文件即可

### mshtmObject.jQuery()

无参数时返回jQuery类对�?
首次调用按需加载 jQuery v1.9:

"/res/js/jQuery/jQuery.min.js"

失败则通过网络CDN服务器下载jquery-1.9.0.min.js

[返回对象:jQueryObject](#jQueryObject)

### mshtmObject.jsConstructor("Array")

获取 JS 使用 new 语句创建对象的构造函数�?
参数 @1 可以�?JS 对象，或字符串类型的对象名字�?
### mshtmObject.jsNew("Array")

调用 JS �?new 语句构�?JS 对象�?
参数 @1 可以�?JS 对象，或字符串类型的对象名字�?
可指定一个或多个构造参数�?
### mshtmObject.loadScript("js地址","框架名字")

动态加载js文件

### mshtmObject.loadScript("js地址","框架名字","utf-8")

动态加载js文件\\N可选用第三个参数指定文件编�?
### mshtmObject.loadcode(HTML模板代码)

使用 aardio 模板语法加载HTML文件

可选在第二个参数中传入模板参数,

模板代码中使用owner参数获取首个模板参数

### mshtmObject.post("字符串参�?,"k=v&k2=v2")

自动提交表单

### mshtmObject.post("字符串参�?,"k=v&k2=v2","自定义http�?)

自动提交表单

### mshtmObject.post("字符串参�?,"k=v&k2=v2","自定义http�?,"目标框架")

自动提交表单

### mshtmObject.queryEles

搜索节点对象,该函数返回的是一个数�?

但可以通过调用数组的成员函数批量调用节点的同名成员函数,支持click函数,

即使找不到节�?此函数也会返回一个空数组,

### mshtmObject.queryEles()

[返回对象:webFormElesObject](#webFormElesObject)

[返回对象:webFormElesObject](#webFormElesObject)

### mshtmObject.queryEles(查询参数�?超时�?

搜索节点对象,该函数返回的是一个数�?

但可以通过调用数组的成员函数批量调用节点的同名成员函数,支持click函数

参数@1指定一个表对象�?
该参数表可包含一个或多个键值，用于匹配节点的属性�?

可使用parent属性指定开始查询节点的父节点，parent可以是ID或者节点对象�?
属性值使�?string.cmpMatch函数进行比对�?
等价于调用string.cmp函数进行忽略大小写的比较,

并且在失败后调用 string.match函数使用模式匹配语法进行比较�?
注意在匹配节点属性时有几个例外：

parent属性不使用模式匹配进行比对�?
tagName,id,name属性如果匹配值不含标点则使用忽略大小写的完全比对（禁用模式匹配和部分匹配�?
可选使用参数@2指定获取网页文档对象的超时值，单位毫秒，此参数一般不需要指�?
### mshtmObject.querySelector("CSS选择�?)

查询并返回节�?
web.form �?Win7，IE8 开始支持该函数

### mshtmObject.querySelector()

[返回对象:eleObject](#eleObject)

### mshtmObject.querySelectorAll("CSS选择�?)

查询并返回节点集�?
web.form �?Win7，IE8 开始支持该函数

### mshtmObject.querySelectorAll()

[返回对象:eleObject](#eleObject)

### mshtmObject.script

网页脚本对象

[返回对象:jsGlobalObject](#jsGlobalObject)

### mshtmObject.type

返回当前加载的文件类�?
例如doc文件返回Microsoft Word Document

### mshtmObject.waitDoc()

```aardio aardio
document.

```

### mshtmObject.waitEle("字符串参�?)

返回一个节点对像或框架内子节点对像

并等待加载完�?
### mshtmObject.waitEle("字符串参�?,"字符串参�?,20000)

返回一个节点对�?
第三个参数指定超时�?毫秒)

### mshtmObject.waitEle()

[返回对象:eleObject](#eleObject)

### mshtmObject.waitQueryEles()

[返回对象:webFormElesObject](#webFormElesObject)

### mshtmObject.waitQueryEles(参数�?超时,时间间隔,完全加载)

参数@1指定一个表对象�?
该参数表可包含一个或多个键值，用于匹配节点的属性�?

可使用parent属性指定开始查询节点的父节点，parent可以是ID或者节点对象�?
属性值使�?string.cmpMatch函数进行比对�?
等价于调用string.cmp函数进行忽略大小写的比较�?
并且在失败后调用 string.match函数使用模式匹配语法进行比较�?
注意在匹配节点属性时有几个例外：

parent属性不使用模式匹配进行比对�?
tagName,id,name属性如果匹配值不含标点则使用忽略大小写的完全比对（禁用模式匹配和部分匹配�?
可选使用参数@2指定超时值，单位毫秒�?其他参数可�?
### mshtmObject.waitQuerySelector("CSS选择�?,框架,超时,是否等待完成)

等待指定节节�?
web.form �?Win7，IE8 开始支持该函数�?
除参数@1以外，其他参数可�?
### mshtmObject.waitQuerySelector()

[返回对象:eleObject](#eleObject)

### mshtmObject.write("字符串参�?)

将字符串值写入网页、不允许追加

将字符串值写入网�?
通过字符串参数载入HTML文件源码

### mshtmObject.write("字符串参�?,"框架�?)

将字符串值写入框架网页、不允许追加

将字符串值写入框架网页、不允许追加

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/web/mshtml.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/web/mshtml.md')

