[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Selenium.NET

```aardio aardio
 //使用 Selenium 实现网页自动化操�?import console;
console.showLoading(" 正在启动 Selenium .NET ");

/*
�?aardio 里用 chrome.driver 更简单一些�?aardio 实际不需要任何第三方组件即可调用 ChromeDriver�?
dotNet.Selenium 基于开源的 Selenium .NET 版本，一些小的改进：
1、自动检测并配置运行环境，自动匹�?Chrome 版本下载对应版本�?ChromeDriver�?2、自动兼容系统安装的 Chrome �?Edge Chromium，自动选择 ChromeDriver �?EdgeDriver
3、内存加载所�?DLL ，可以生成绿色独立的 EXE 文件�?*/
import dotNet.Selenium;

//简单化创建 WebDriver 对象
var wd = Selenium.CreateDefaultWebDriver();

//打开网址�?wd.Url = "https://www.aardio.com/zh-cn/doc/"

//By 对象用于创建查找节点的条件对象�?var By = Selenium.By;

/*
查找并等待输入框节点�?Selenium 自己提供�?WebDriverWait 不好用，这个 WaitEle 函数是用 aardio 实现的�?*/
var keyword = wd.WaitEle( By.Id("search-input")  )

//清空输入�?keyword.Clear();

//发送按�?keyword.SendKeys("多线�?);

//查找按钮
var button = wd.FindElement( By.Id("search-button") );

//点击按钮
button.Click();

//获取 cookie
var cookies = wd.Manage().Cookies.AllCookies;

//�?dotNet 遍历 .NET 数组
for i,cookie in dotNet.each(cookies) {
    console.log(cookie.Name)
    console.log(cookie.Value)
    console.log(cookie.Domain)
}

//截图
wd.GetScreenshot().SaveAsFile(io.fullpath("/baidu.png") );
//上面�?个参�?0 ,也可以用枚举 SeleniumBasic.Utility.ScreenshotImageFormat.Png 获取

console.close();
console.log(wd.Title, wd.Url);
console.log(wd.PageSource);
console.pause(,"按任意键退出浏览器");

//退出浏览器
wd.Quit();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/Selenium.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/Selenium.md')

