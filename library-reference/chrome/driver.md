[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# chrome.driver 库模块帮助文�?
说明

[WebDriver 协议](https://w3c.github.io/webdriver) [JSON wire protocol 协议](https://www.selenium.dev/documentation/legacy/json_wire_protocol)
JSON wire protocol 仅供参考，�?WebDriver 文档为准�?
此支持库会优先使用系统自带的 Edge（Chromium）浏览器�?不同版本浏览器需要下载不同版本的 chromedriver.exe （Edge 则为 msedgedriver.exe）�?
如果 chrome.exe 所在目录已经存�?chromedriver.exe 则直接使用该路径�?否则 aardio 会自动检测并下载匹配版本�?msedgedriver.exe�?
aardio 不会�?msedgedriver 或chromedriver 下载地址失效、变动导致的后果承担任何责任，如不同意请不要使用�?
Win7,XP 等旧系统建议手动安装兼容�?Chromium 内核�?Supermium 浏览器（安装时不要修改安装路径）�?
## chrome 成员列表

### chrome.driver()

[返回对象:chromeDriverObject](#chromeDriverObject)

### chrome.driver(browserPath)

创建并返�?ChromeDriver 对象，失败返�?null，错误信息�?
参数@1如果不指�?Chrome �?Edge 路径,aardio会自动获取浏览器路径�?
aardio会自动搜索浏览器同目录下的适合�?\*\*\*\*driver.exe�?
如果指不到会自动获到浏览器的版本并自动下载对应版本的�?chromedriver.exe �?edgedriver.exe�?
n可选使用参�?@3 自定义下载对话框标题

### chrome.driver(browserPath,driverPath)

创建并返�?ChromeDriver 对象，失败返�?null，错误信息�?
如果不指定参�?@browserPath，则只能通过远程调试端口直接连接

### chrome.driver(browserPath,driverVersion)

创建并返�?ChromeDriver 对象，失败返�?null，错误信息�?
如果不指定参数@1，则只能通过远程调试端口直接连接,

参数 @driverVersion 必须使用一个字符串或一个数值指�?Chrome �?Edge 的主版本�?
### chrome.driver(true)

创建并返�?ChromeDriver 对象，失败返�?null，错误信息�?
优先获取 Chrome 路径，如果找不到则获�?Edge 路径�?
如果参数 @1 不指定路径且不为 true ，则优先获取 Edge 路径�?
aardio会自动搜索浏览器同目录下的适合�?\*\*\*\*driver.exe�?
如果指不到会自动获到浏览器的版本并自动下载对应版本的�?chromedriver.exe �?edgedriver.exe�?
n可选使用参�?@3 自定义下载对话框标题

## chrome.driver 成员列表

用于调用 ChromeDriver �?EdgeDriver 自动化控制内核浏览器 �?
兼容 Chrome ，Edge ，Supermium �?Chromium 内核浏览器�?
aardio会自动搜索浏览器同目录下的适合�?\*\*\*\*driver.exe�?
如果指不到会自动获到浏览器的版本并自动下载对应版本的�?chromedriver.exe �?edgedriver.exe�?
aardio 不会�?ChromeDriver 下载地址失效、变动导致的后果承担任何责任，如不同意请不要使用�?
版本号不兼容的其他浏览器请自行指�?chromedriver.exe 路径

创建并返�?ChromeDriver 对象，失败返�?null，错误信息�?
### chrome.driver.KEYS

这是一个表�?
表的键值定义了可用�?sendKeys 函数的键名与键值�?
键名与标准库 key,key.VK 基本兼容，但键值是不同�?
### chrome.driver.chromePath

Chrome.exe 或浏览器主程序路�?
### chrome.driver.driverPath

chromedriver.exe �?msedgedriver.exe 路径

### chrome.driver.requirePath()

参数@1使用字符串传入Chrome版本�?

返回匹配的ChromeDriver路径

如果未安装该版本ChromeDriver会自动下载安�?
可选使用参数@2自定义下载对话框标题

## chromeDriverEleObject 成员列表

### chromeDriverEleObject.?

可输入任意资源名

对象负责转换为资源请求URL

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverEleObject.attribute

标签属性集合�?
使用下标或成员操作符指定属性名，例如：

attribute\["属性名"\].get() 返回对象�?value 字段为属性�?
### chromeDriverEleObject.clear()

清空节点

### chromeDriverEleObject.click()

模拟点击

### chromeDriverEleObject.delete

DELETE方法提交请求,删除资源

调用时可以写 delete() �?delete.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverEleObject.get

GET方法提交请求,获取资源

调用时可以写 get() �?get.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverEleObject.getAttribute()

返回 HTML 标签属性值，成功返回字符串值，否则�?null �?
### chromeDriverEleObject.getName()

返回 name 属性�?
### chromeDriverEleObject.getProperty()

返回节点属性�?
### chromeDriverEleObject.getRect()

返回一个表示节点区块位置的 ::RECT 结构�?
### chromeDriverEleObject.getSize()

返回一个表示节点大小的 ::SIZE 结构�?
### chromeDriverEleObject.getStyle()

返回 CSS 样式指定属性值，参数 @1 指定属性名

### chromeDriverEleObject.getValue()

返回文本�?
### chromeDriverEleObject.head

HEAD方法提交请求

如果该函数返回非null值为成功,请使用lastResponseHeaders获取应答HTTP�?
调用时可以写 head() �?head.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

### chromeDriverEleObject.innerText()

获取节点文本

### chromeDriverEleObject.isDisplayed()

节点是否显示

### chromeDriverEleObject.isEnabled()

节点是否启用

### chromeDriverEleObject.isSelected()

节点是否选中

### chromeDriverEleObject.patch

PATCH方法提交请求,更新资源

调用时可以写 patch() �?patch.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverEleObject.post

POST方法提交请求,新增或修改资�?
调用时可以写 post() �?post.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverEleObject.property

属性集合�?
使用下标或成员操作符指定属性名，例如：

attribute\["属性名"\].get() 返回对象�?value 字段为属性�?
### chromeDriverEleObject.put

PUT方法提交请求,替换或更新资�?
调用时可以写 put() �?put.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverEleObject.query()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverEleObject.query(查询参数)

```aardio aardio
chromeDriverEleObject.query(["partial link text"]="链接文本"/*使用指定键值对查询网页元素,不指定参数获取当前活动元�?/)

```

### chromeDriverEleObject.queryAll()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverEleObject.queryAll(查询参数)

```aardio aardio
chromeDriverEleObject.query(["partial link text"]="链接文本"/*使用指定键值对查询并返回网页元素数�?/)

```

### chromeDriverEleObject.querySelector("字符串参�?)

指定CSS选择器并返回节点对象

HTTP接口：POST /session/{session id}/element/{element id}/element

### chromeDriverEleObject.querySelector()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverEleObject.querySelectorAll("字符串参�?)

指定CSS选择器并返回节点对象数组

HTTP接口：POST /session/{session id}/element/{element id}/elements

### chromeDriverEleObject.querySelectorAll()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverEleObject.sendKeys()

在该节点发送按键�?
参数可指定一个或多个键名，也要吧用一个字符串数组指定一个或多个键名�?
可用键名�?chrome.driver.KEYS 定义的键名�?
其他字符串直接发�?
### chromeDriverEleObject.setValue()

使用一个或多个字符串参数指定要发送的文本�?
如果要发�?chrome.driver.KEYS 定义的按键，必须指定对应键名的键值�?
改用 sendKeys 函数可在参数中指定键�?
### chromeDriverEleObject.submit()

提交表单

### chromeDriverEleObject.waitEle("字符串参�?)

等待并返回指�?CSS 选择器匹配的节点对象�?
可选用参数 @2 指定超时（毫秒），可选用参数 @3 指定检测间隔（毫秒）�?
HTTP接口：POST /session/{session id}/element

## chromeDriverEleObject.attribute.? 成员列表

### chromeDriverEleObject.attribute.?.get()

获取attribute�?
HTTP接口：GET /session/{session id}/element/{element id}/attribute/{name}

## chromeDriverEleObject.property.? 成员列表

### chromeDriverEleObject.property.?.get()

获取property�?
HTTP接口：GET /session/{session id}/element/{element id}/attribute/{name}

## chromeDriverEleObject.screenshot 成员列表

### chromeDriverEleObject.screenshot.get()

截屏

HTTP接口：GET /session/{session id}/element/{element id}/screenshot

## chromeDriverEleObject.selected 成员列表

### chromeDriverEleObject.selected.get()

是否选中

HTTP接口：GET /session/{session id}/element/{element id}/selected

## chromeDriverObject 成员列表

### chromeDriverObject.addArguments()

添加一个或多个Chrome启动参数,

参数也可以是一个包含多个启动参数的数组

注意参数中不必要使用引号,多个参数应分开写不要拼接成一个参�?
每个启动参数都是使用两个横杠开始的字符�?
[chrome启动参数大全](https://peter.sh/experiments/chromium-command-line-switches/)

### chromeDriverObject.attach()

[返回对象:chromeDriverSesObject](#chromeDriverSesObject)

### chromeDriverObject.attach(debuggerPort,desiredCap,requiredCap)

附加到debuggerPort指定的调试端�?返回该会话的REST API对象,

如果创建chrome.driver的第一个参数是electron.app或chrome.app,debuggerPort参数可以不指�?
其他参数可�?
### chromeDriverObject.chromePath

浏览器程序路�?
### chromeDriverObject.client

WebDriver API

[返回对象:webRestClientObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestClientObject)

web.rest.jsonClient客户端对�?
[返回对象:webRestClientObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestClientObject)

### chromeDriverObject.clientApi

WebDriver API

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverObject.close()

关闭ChromeDriver服务�?

程序退出前也会自动关闭ChromeDriver服务�?
### chromeDriverObject.createBrowser(desiredCap,requiredCap)

打开Chrome并创建会�?返回会话信息,

startBrowser会自动调用此函数,参数用法参考startBrowser

### chromeDriverObject.debuggerAddress

指定Chrome远程调试地址�?
格式�?IP或主�?端口号，例如 127.0.0.1:38947

Chrome Driver将直接附加到该浏览器实例

### chromeDriverObject.debuggerPort

指定Chrome远程调试端口

Chrome Driver将直接附加到该浏览器实例

### chromeDriverObject.driverPath

\*\*\*\*driver.exe 程序路径

### chromeDriverObject.getCapabilities()

返回浏览器创建会话的desiredCap默认参数

可选在参数中自定义部分字段

### chromeDriverObject.isHeadless

启动参数是否指定�?--headless

### chromeDriverObject.lastRequestUrl()

返回最后一次请求的URL

### chromeDriverObject.lastResponse()

返回最后一次响应的内容

### chromeDriverObject.removeArguments()

排除一个或多个Chrome启动参数,

参数也可以是一个包含多个启动参数的数组

### chromeDriverObject.server

服务端进�?process.poen 对象

[返回对象:processPopenObject](https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html#processPopenObject)

### chromeDriverObject.setOptions()

设置Chrome启动选项,参数应当是键值对组成的表

[ChromeDriver选项文档](http://chromedriver.chromium.org/capabilities)

### chromeDriverObject.setProxy(代理配置)

```aardio aardio
chromeDriverObject.setProxy(
    proxyType = "manual";
    httpProxy = "127.0.0.1:12043"
)

```

### chromeDriverObject.startAppBrowser

打开 Chrome 并创�?APP 模式会话,返回该会话的 REST API对象

### chromeDriverObject.startAppBrowser()

[返回对象:chromeDriverSesObject](#chromeDriverSesObject)

### chromeDriverObject.startAppBrowser(app,args,desiredCap,requiredCap)

打开Chrome并创建APP模式会话,返回该会话的REST API对象

app应当是一个chrome.app对象,args是包含chrome启动参数的数�?
其他参数为可选参�?
### chromeDriverObject.startAppBrowser(url,desiredCap,requiredCap)

打开Chrome并创建APP模式会话,返回该会话的REST API对象

url指定要打开的网址,其他参数为可选参�?
### chromeDriverObject.startBrowser

打开Chrome并创建会�?返回该会话的REST API对象

### chromeDriverObject.startBrowser()

[返回对象:chromeDriverSesObject](#chromeDriverSesObject)

### chromeDriverObject.startBrowser(desiredCap,requiredCap)

打开Chrome并创建会�?返回该会话的REST API对象,

参数可�?aardio自动添加必要的默认参�?

参数用法参考文�?
[Chrome选项文档](http://chromedriver.chromium.org/capabilities)

### chromeDriverObject.startServer

启动ChromeDriver服务�?
### chromeDriverObject.startServer()

[返回对象:processPopenObject](https://www.aardio.com/zh-cn/doc/library-reference/process/popen.html#processPopenObject)

### chromeDriverObject.startServer(端口,其他启动参数)

启动ChromeDriver服务�?所有参数可�?

不指定端口时自动分配空闲端口,不会与其他程序冲�?
如果指定参数@2会作为process.popen的附加启动参�?

返回process.popen对象

## chromeDriverSesObject 成员列表

### chromeDriverSesObject.?

可输入任意资源名

对象负责转换为资源请求URL

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverSesObject.actions()

执行动作

HTTP接口：POST /session/{session id}/actions

### chromeDriverSesObject.back()

后退

HTTP接口：POST /session/{session id}/back

### chromeDriverSesObject.cdp

执行 CDP 命令�?
调用成功则第一个返回值为 CDP 返回的表对象�?
调用失败则第二个返回值为错误信息�?
注意 CDP 调用成功不等于命令执行成功，

即使调用成功且第一个返回值为表对象，

该返回值仍解码器能包含错误状态码与错误信息�?
返回表对象的字段含义请参�?CDP 文档�?
HTTP接口：POST /session/{session id}/goog\|ms/cdp/execute

### chromeDriverSesObject.close()

关闭当前会话的当前活动浏览器窗口（输入焦点所在窗口）

### chromeDriverSesObject.closeAll()

关闭会话创建的所有浏览器窗口

### chromeDriverSesObject.cookie()

修改cookie

HTTP接口：POST /session/{session id}/cookie

### chromeDriverSesObject.delete

DELETE方法提交请求,删除资源

调用时可以写 delete() �?delete.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverSesObject.delete()

删除会话

DELETE /session/{session id}

### chromeDriverSesObject.doScript

执行脚本

HTTP接口：POST /session/{session id}/execute/sync

### chromeDriverSesObject.doScript("JS脚本",其他调用参数)

JS脚本会被放到一个匿名函数中执行,

可添加任意个调用参数,节点对象可作为参�?
成功返回该匿名函数的返回�?

失败返回null,以及REST API返回的响应对�?
### chromeDriverSesObject.eachWindow()

```aardio aardio
for( index,window,title,url in chromeDriverSesObject.eachWindow() ){
    /*遍历所有窗�?已自动切换焦点到当前遍历的窗�?/
}

```

### chromeDriverSesObject.findTitle()

查找并等待出现网页窗口标题并切换到该窗口,

参数指定窗口标题,支持模式匹配语法,成功返回 true

### chromeDriverSesObject.findUrl()

使用网址查找网页窗口并切换到该窗�?

参数指定网址,支持模式匹配语法,成功返回true

### chromeDriverSesObject.forward()

前进

HTTP接口：POST /session/{session id}/forward

### chromeDriverSesObject.frame(id="字符串参�?)

切换框架�?
id 参数可指�?string,number,null,WebElement JSON Object 等类型�?
细节请参�?WebDriver 文档�?
HTTP接口：POST /session/{session id}/frame

### chromeDriverSesObject.get

GET方法提交请求,获取资源

调用时可以写 get() �?get.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverSesObject.getCurrentTitle()

获取当前网页窗口标题，成功返回字符串

### chromeDriverSesObject.getCurrentUrl()

获取当前URL，成功返回字符串

### chromeDriverSesObject.getCurrentWindow()

获取当前网页窗口句柄标识，成功返回字符串

### chromeDriverSesObject.go("字符串参�?)

打开指定网址

HTTP接口：GET /session/{session id}/url

### chromeDriverSesObject.head

HEAD方法提交请求

如果该函数返回非null值为成功,请使用lastResponseHeaders获取应答HTTP�?
调用时可以写 head() �?head.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

### chromeDriverSesObject.isHeadless

启动参数是否指定�?--headless

### chromeDriverSesObject.loadScript("字符串参�?)

加载JS脚本文件

参数指定JS文件网址

此函数发送请求后立即返回,不会等待脚本加载完成

### chromeDriverSesObject.notify

```aardio aardio
chromeDriverSesObject.notify(
    function(){
        /*此函数中执行的请求不阻塞，并且忽略返回�?/
    }
)

```

### chromeDriverSesObject.patch

PATCH方法提交请求,更新资源

调用时可以写 patch() �?patch.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverSesObject.post

POST方法提交请求,新增或修改资�?
调用时可以写 post() �?post.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverSesObject.put

PUT方法提交请求,替换或更新资�?
调用时可以写 put() �?put.其他资源�?)

请求参数可以指定表或字符�?如果是表请求前会转换为字符串

[返回对象:webRestApiObject](https://www.aardio.com/zh-cn/doc/library-reference/web/rest/client.html#webRestApiObject)

### chromeDriverSesObject.query()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverSesObject.query(查询参数)

```aardio aardio
chromeDriverSesObject.query(["partial link text"]="链接文本"/*使用指定键值对查询网页元素,不指定参数获取当前活动元�?/)

```

### chromeDriverSesObject.queryAll()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverSesObject.queryAll(查询参数)

```aardio aardio
chromeDriverSesObject.query(["partial link text"]="链接文本"/*使用指定键值对查询并返回网页元素数�?/)

```

### chromeDriverSesObject.querySelector("字符串参�?)

指定CSS选择器并返回节点对象

HTTP接口：POST /session/{session id}/element

### chromeDriverSesObject.querySelector()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverSesObject.querySelectorAll("字符串参�?)

指定CSS选择器并返回节点对象数组

HTTP接口：POST /session/{session id}/elements

### chromeDriverSesObject.querySelectorAll()

[返回对象:chromeDriverEleObject](#chromeDriverEleObject)

### chromeDriverSesObject.refresh()

前进

HTTP接口：POST /session/{session id}/refresh

### chromeDriverSesObject.sendKeys()

在活动节点发送按键�?
参数可指定一个或多个键名，也可用一个字符串数组指定一个或多个键名�?
可用键名�?chrome.driver.KEYS 定义的键名�?
不是键名的其他字符串作为普通文本直接发送�?
### chromeDriverSesObject.sessionInfo

浏览器会话信�?
### chromeDriverSesObject.switchWindow()

切换窗口,

参数@1可用字符串指定窗口句柄标�?

也可以用数值参数指定窗口索引�?
成功返回 true

### chromeDriverSesObject.timeouts()

设置超时

HTTP接口：POST /session/{session id}/timeouts

### chromeDriverSesObject.waitEle("字符串参�?)

等待并返回指�?CSS 选择器匹配的节点对象�?
可选用参数 @2 指定超时（毫秒），可选用参数 @3 指定检测间隔（毫秒）�?
HTTP接口：POST /session/{session id}/element

### chromeDriverSesObject.waitTitle()

等待指定标题的网页窗口并切换到该窗口�?
参数 @1 指定窗口标题，支持模式匹配语法�?
可选用参数 @2 指定超时（毫秒），可选用参数 @3 指定检测间隔（毫秒）�?
成功返回true

### chromeDriverSesObject.waitUrl()

等待指定网址的网页窗口并切换到该窗口�?
参数 @1 指定网址，支持模式匹配语法�?
可选用参数 @2 指定超时（毫秒），可选用参数 @3 指定检测间隔（毫秒）�?
成功返回true

### chromeDriverSesObject.waitUrlParam("字符串参�?,"字符串参�?)

等待参数@1指定的网址打开，支持模式匹配�?
参数 @1 的等待规则与 waitUrl 函数相同�?
参数 @2 指定要等待的 URL 参数名，

如果找到该参数则返回参数值，否则继续等待到参数出现或社会窗口关闭

### chromeDriverSesObject.window()

切换窗口

HTTP接口：POST /session/{session id}/window

## chromeDriverSesObject.actions 成员列表

### chromeDriverSesObject.actions.delete()

删除动作

DELETE /session/{session id}/actions

## chromeDriverSesObject.alert 成员列表

### chromeDriverSesObject.alert.accept()

取消alert

HTTP接口：POST /session/{session id}/alert/accept

### chromeDriverSesObject.alert.dismiss()

取消alert

HTTP接口：POST /session/{session id}/alert/dismiss

### chromeDriverSesObject.alert.text()

发送alert文本

HTTP接口：POST /session/{session id}/alert/text

## chromeDriverSesObject.alert.text 成员列表

### chromeDriverSesObject.alert.text.get()

获取alert文本

HTTP接口：GET /session/{session id}/alert/text

## chromeDriverSesObject.browser 成员列表

浏览器自定义命令接口�?
Edge 浏览器为 /session/{session id}/ms �?
Chrome 浏览器为 /session/{session id}/goog

### chromeDriverSesObject.browser.name

浏览器名称，Edge 浏览器为 "MicrosoftEdge" �?"chrome"

### chromeDriverSesObject.browser.userDataDir

用户数据目录

### chromeDriverSesObject.browser.version

浏览器版�?
## chromeDriverSesObject.chromium 成员列表

### chromeDriverSesObject.chromium.network\_conditions()

修改用于仿真的网络条�?
session/:session\_id/chromium/network\_conditions

## chromeDriverSesObject.chromium.network\_conditions 成员列表

### chromeDriverSesObject.chromium.network\_conditions.get()

获取用于仿真的网络条�?
session/:session\_id/chromium/network\_conditions

## chromeDriverSesObject.cookie 成员列表

### chromeDriverSesObject.cookie.delete()

删除cookie,

也可以写为cookie.name.delete删除指定名字cookie

DELETE /session/{session id}/cookie/{name}

### chromeDriverSesObject.cookie.get()

获取cookie,也可以写为cookie.name.get

HTTP接口：GET /session/{session id}/cookie

## chromeDriverSesObject.execute 成员列表

### chromeDriverSesObject.execute.async()

异步执行脚本

HTTP接口POST /session/{session id}/execute/async

## chromeDriverSesObject.frame 成员列表

### chromeDriverSesObject.frame.parent()

切换到父框架，无参数�?
如果当前已经是顶层框架则忽略此调用�?
HTTP接口：POST /session/{session id}/frame/parent

## chromeDriverSesObject.screenshot 成员列表

### chromeDriverSesObject.screenshot.get()

截屏

HTTP接口：GET /session/{session id}/screenshot

## chromeDriverSesObject.se 成员列表

### chromeDriverSesObject.se.log()

返回日志,

使用一个表参数并在types字段里指定要获取的日志类�?
## chromeDriverSesObject.se.log.types 成员列表

### chromeDriverSesObject.se.log.types.get()

返回可用日志类型

## chromeDriverSesObject.source 成员列表

### chromeDriverSesObject.source.get()

获取页面源码

HTTP接口：GET /session/{session id}/source

获取页面源码

HTTP接口：GET /session/{session id}/source

## chromeDriverSesObject.status 成员列表

### chromeDriverSesObject.status.get()

获取当前状�?
HTTP接口：GET /status

## chromeDriverSesObject.timeouts 成员列表

### chromeDriverSesObject.timeouts.get()

获取超时

HTTP接口：GET /session/{session id}/timeouts

## chromeDriverSesObject.title 成员列表

### chromeDriverSesObject.title.get()

获取标题

HTTP接口：GET /session/{session id}/title

## chromeDriverSesObject.url 成员列表

### chromeDriverSesObject.url.get()

获取当前URL

HTTP接口：GET /session/{session id}/url

## chromeDriverSesObject.window 成员列表

### chromeDriverSesObject.window.delete()

关闭当前窗口

DELETE /session/{session id}/window

### chromeDriverSesObject.window.get()

获取当前窗口

HTTP接口：GET /session/{session id}/window

### chromeDriverSesObject.window.maximize()

最大化

HTTP接口：POST /session/{session id}/window/maximize

### chromeDriverSesObject.window.minimize()

最小化

HTTP接口：POST /session/{session id}/window/minimize

### chromeDriverSesObject.window.rect()

前进\\POST /session/{session id}/window/rect

## chromeDriverSesObject.window.handles 成员列表

### chromeDriverSesObject.window.handles.get()

获取所有窗口句�?
HTTP接口：GET /session/{session id}/window/handles

## chromeDriverSesObject.window.rect 成员列表

### chromeDriverSesObject.window.rect.get()

获取窗口位置

HTTP接口：GET /session/{session id}/window/rect

[Markdown 格式](https://www.aardio.com/zh-cn/doc/library-reference/chrome/driver.md)

