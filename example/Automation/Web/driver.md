[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用 chrome.driver 实现网页自动化操�?
```aardio aardio
//使用 chrome.driver 实现网页自动化操�?import chrome.driver;

/*
创建 chromeDriver 对象，支 Chrome，Edge（Chromium），Supermium 等相同内核浏览器�?自动检�?chromeDriver 版本，并在必要时自动下载匹配版本的chromeDriver�?*/
var driver = chrome.driver();
//协议文档 https://w3c.github.io/webdriver
//更多用法 https://bbs.aardio.com/forum.php?mod=viewthread&tid=22544

//排除参数，不显示"正受到自动测试软件的控制"，老版�?Chrome 可能会有更大的弹框，新版没问�?//driver.removeArguments("--enable-automation")

//添加 Chrome 启动参数
//driver.addArguments("--start-maximized")
//driver.addArguments("--incognito") //无痕模式
//driver.addArguments("--headless") //无痕模式，看不到界面

/*
Chrome 启动参数参�?
https://peter.sh/experiments/chromium-command-line-switches/
*/

//创建会话，打开chrome浏览器，调用参数仅用于演�? 可以省略 )�?var browser = driver.startBrowser( {
    loggingPrefs  = { browser = 'ALL', performance = 'ALL', };
    perfLoggingPrefs = {
        enableNetwork = true,
        enablePage= false,
        enableTimeline = false
    }
});

//打开网页
browser.go("https://www.aardio.com/zh-cn/doc/")

//查找文本输入�?返回�?DOM 对象也可以使用ququerySelector继续查找子节�?var ele = browser.querySelector("body").querySelector("#search-input");

//在网页输入文本，并发送按键�?ele.sendKeys( "多线�? ,"ENTER"  )

/*
可用键名定义�?chrome.driver.keys ，键名与 key,key.VK 库基本兼容�?如果要将键名设为普通文本，可改�?ele.setValue( "ChromeDriver","ENTER" )
*/

//调用 JS，并且可以返回值（也可以返�?DOM 节点对象�?var searchButton = browser.doScript(`
        //可以使用arguments访问aardio传来的参�?        return arguments[0].querySelector("#search-button");
    `
    ,browser.querySelector("body")//可以传任意个调用参数给JS,还可以直接传DOM节点对象
)

//JS 返回�?DOM 节点对象也可以操作控�?searchButton.click();

//等待网址
browser.waitUrl("多线�?);

//打开新窗�?标签�?
browser.doScript("window.open('https://httpbin.org/cookies')");

//关闭原来的窗�?标签�?
browser.close();

//等待网址
browser.waitUrl("httpbin");

//修改 cookie
var ret,err = browser.cookie( {
    cookie = { name = "GUID",value = "09031171412667840400",domain="httpbin.org"}
} )

//调用 CDP 命令
var ret,err = browser.cdp("Network.getCookies",{urls={"https://httpbin.org"}},);
var cookies = ret[["value"]];

//driver.startBrowser() 指定 loggingPrefs, perfLoggingPrefs
//var log = browser.se.log(type="performance"); //获取日志

browser.refresh();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Automation/Web/driver.md)

