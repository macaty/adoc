[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Web Form - 鐩戝惉瑙﹀彂浜嬩欢

```aardio aardio
//鐩戝惉瑙﹀彂浜嬩欢
import win.ui;
/*DSG{{*/
var winform = win.form(text="Web Form - 鐩戝惉瑙﹀彂浜嬩欢";right=759;bottom=469)
winform.add()
/*}}*/

//鍒涘缓娴忚鍣ㄦ帶浠?import web.form;
var wb = web.form( winform );

wb.html = /**
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
</head>
<body>
    <textarea id="textarea-id" rows="10" cols="60">璇峰湪杩欓噷杈撳叆鏂囨湰</textarea>

    <br>淇敼浼氬悓姝ュ弽棣堝埌涓嬮潰:<br>
    <textarea id="textarea-id2" rows="10" cols="60"></textarea>
</body>
</html>
**/

//绛夊緟缃戦〉鎵撳紑
wb.wait();

//鐩戝惉浜嬩欢
wb.attach(
    function(event){
        wb.getEle("textarea-id2").innerText = event.srcElement.innerText;
    }
    ,"keydown","textarea-id"
)

//鐩戝惉浜嬩欢
wb.attach(
    function(event){
        wb.getEle("textarea-id2").innerText = "涓婇潰textarea鐨勬枃鏈凡鍙樻洿涓猴細 " + event.srcElement.innerText;
    }
    ,"change","textarea-id"
)

//涓诲姩瑙﹀彂浜嬩欢
wb.dispatchEvent("textarea-id","change");

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/dispatchEvent.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/web.form/Automation/dispatchEvent.md')

