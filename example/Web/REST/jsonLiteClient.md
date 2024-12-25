[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: web.rest 客户�?- web.rest.jsonLiteClient

```aardio aardio
//web.rest 客户�?- web.rest.jsonLiteClient
import win.ui;
/*DSG{{*/
var winform = win.form(text="获取取京东商品评�?;right=1189;bottom=593)
winform.add(
edit={cls="edit";left=10;top=6;right=1179;bottom=575;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import web.rest.jsonLiteClient;
var http = web.rest.jsonLiteClient()

http.referer = "https://item.jd.com/"
var jdClub = http.api("https://club.jd.com/comment/productPageComments.action?callback=fetchJSON_comment98vv13283")

var data = jdClub.get(
    productId="100004253893"; // 商品编号
    sortType=6; // 5表示推荐排序,6为按时间排序
    isShadowSku=0; // 仅显示当前商品评�?    score=3; // 好评
    page=1; // 分页索引
    pageSize=10;
    fold=1;
    rid=0;
)

winform.edit.print(data);

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/jsonLiteClient.md)

