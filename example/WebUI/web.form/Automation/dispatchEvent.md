[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Web Form - 监听触发事件

```aardio aardio
//监听触发事件
import win.ui;
/*DSG{{*/
var winform = win.form(text="Web Form - 监听触发事件";right=759;bottom=469)
winform.add()
/*}}*/

//创建浏览器控�?import web.form;
var wb = web.form( winform );

wb.html = /**
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
</head>
<body>
    <textarea id="textarea-id" rows="10" cols="60">请在这里输入文本</textarea>

    <br>修改会同步反馈到下面:<br>
    <textarea id="textarea-id2" rows="10" cols="60"></textarea>
</body>
</html>
**/

//等待网页打开
wb.wait();

//监听事件
wb.attach(
    function(event){
        wb.getEle("textarea-id2").innerText = event.srcElement.innerText;
    }
    ,"keydown","textarea-id"
)

//监听事件
wb.attach(
    function(event){
        wb.getEle("textarea-id2").innerText = "上面textarea的文本已变更为： " + event.srcElement.innerText;
    }
    ,"change","textarea-id"
)

//主动触发事件
wb.dispatchEvent("textarea-id","change");

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/dispatchEvent.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/dispatchEvent.md')
