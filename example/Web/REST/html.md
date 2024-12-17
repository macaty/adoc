[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: web.rest 瀹㈡埛绔?- web.rest.htmlClient

```aardio aardio
//web.rest 瀹㈡埛绔?- web.rest.htmlClient
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

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/html.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/html.md')

