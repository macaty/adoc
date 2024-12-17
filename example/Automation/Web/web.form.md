[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用 web.form 实现网页自动化操�?
```aardio aardio
//使用 web.form 实现网页自动化操�?import win.ui;
/*DSG{{*/
var winform = win.form(text="使用webform调用网页上的对象、函�?;right=848;bottom=585)
winform.add()
/*}}*/

//创建web窗体
import web.form;
var wb = web.form( winform );
wb.noScriptErr = true;

//打开网页
wb.go("https://www.bing.com")

//显示窗口
winform.show();

//等待节点创建成功
wb.waitEle("sb_form_q")
//wb.waitEle("input").value = "aardio web.form"; //这样设置值也�?
//改变节点的默认属性值（这里�?value 属性）,支持 React 文本�?wb.setEle("sb_form_q","web.form");

/*
调用click函数模拟点击按钮�?wb.getEle("search-button").click() 也可�?wb.click()多了一些模拟真实点击的代码，参考此函数源代�?*/
wb.click("search_icon")

/*
等待网页打开,
参数可以指定期待的网址（或者网址的一部分�?*/
wb.wait("q=web.form");

win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Web/web.form.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Web/web.form.md')

