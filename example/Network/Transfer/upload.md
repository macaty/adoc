[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 涓婁紶鏂囦欢

```aardio aardio
//涓婁紶鏂囦欢
import console.int;
import console.progress;
import web.rest.jsonLiteClient;

var http = web.rest.jsonLiteClient();
var api = http.api("https://httpbin.org/post");

//杩涘害鏉?var bar = console.progress();

//浣跨敤鏂囦欢琛ㄥ崟涓婁紶鏂囦欢锛屽彲浠ユ寚瀹氬涓瓧娈?var result = api.sendMultipartForm( {
        file = "@\b.upload.aardio";
    },function(sendData,sendSize,contentLength,remainSize){
        /*
        sendData 涓烘湰娆′笂浼犳暟鎹紱
        sendSize 涓烘湰娆′笂浼犲瓧鑺傛暟锛?        contentLength 涓鸿涓婁紶鐨勬�诲瓧鑺傛暟锛?        remainSize 涓哄墿浣欏瓧鑺傛暟锛?        */

        bar.setProgress((1 - remainSize/contentLength) * 100,"姝ｅ湪涓婁紶 ......");
    }
);

console.dumpJson(result);

//鐩存帴涓婁紶鏂囦欢
var api = http.api("https://httpbin.org/anything");
var result = api.sendFile( "\b.upload.aardio"
    ,function(sendData,sendSize,contentLength,remainSize){
        /*
        sendData 涓烘湰娆′笂浼犳暟鎹紱
        sendSize 涓烘湰娆′笂浼犲瓧鑺傛暟锛?        contentLength 涓鸿涓婁紶鐨勬�诲瓧鑺傛暟锛?        remainSize 涓哄墿浣欏瓧鑺傛暟锛?        */
    }
);

console.dumpJson(result);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/Transfer/upload.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/Transfer/upload.md')

