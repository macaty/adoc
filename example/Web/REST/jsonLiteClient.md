[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: web.rest 瀹㈡埛绔?- web.rest.jsonLiteClient

```aardio aardio
//web.rest 瀹㈡埛绔?- web.rest.jsonLiteClient
import win.ui;
/*DSG{{*/
var winform = win.form(text="鑾峰彇鍙栦含涓滃晢鍝佽瘎璁?;right=1189;bottom=593)
winform.add(
edit={cls="edit";left=10;top=6;right=1179;bottom=575;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import web.rest.jsonLiteClient;
var http = web.rest.jsonLiteClient()

http.referer = "https://item.jd.com/"
var jdClub = http.api("https://club.jd.com/comment/productPageComments.action?callback=fetchJSON_comment98vv13283")

var data = jdClub.get(
    productId="100004253893"; // 鍟嗗搧缂栧彿
    sortType=6; // 5琛ㄧず鎺ㄨ崘鎺掑簭,6涓烘寜鏃堕棿鎺掑簭
    isShadowSku=0; // 浠呮樉绀哄綋鍓嶅晢鍝佽瘎璁?    score=3; // 濂借瘎
    page=1; // 鍒嗛〉绱㈠紩
    pageSize=10;
    fold=1;
    rid=0;
)

winform.edit.print(data);

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/jsonLiteClient.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/jsonLiteClient.md')

