[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: web.rest 客户�?- web.rest.htmlClient

```aardio aardio
//web.rest 客户�?- web.rest.htmlClient
import console.int;
import web.rest.htmlClient;

var htmlDoc = web.rest.htmlClient.get("https://translate.*******.com/m",{
    q="hello",sl="en",tl="zh-CN",hl="zh-CN"
});

if(htmlDoc){
    var resultContainer = htmlDoc.queryEle({"class":"result-container"})

    if(resultContainer){
        console.log(resultContainer.innerText());
    }
}

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/html.md)

