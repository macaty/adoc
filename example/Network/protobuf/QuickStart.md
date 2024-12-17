[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍏ラ棬

```aardio aardio
//鍏ラ棬
import console;
console.showLoading(" 姝ｅ湪涓嬭浇 dm.proto");

import web.rest.github;
var proto = web.rest.github.getContent("SocialSisterYi/bilibili-API-collect/blob/master/grpc_api/bilibili/community/service/dm/v1/dm.proto")

import web.rest.client;
var http = web.rest.client();
var content = http.get("https://api.bilibili.com/x/v2/dm/web/seg.so",{
  "oid":"36570401","pid":"76459310","type":1,"segment_index":1
})

//瑙ｆ瀽 proto 鐢熸垚 aardio 搴?import protobuf.parser;
protobuf.parser().parse(proto,,false);//鍘绘帀鍙傛暟 @3 鍦ㄥ伐绋嬬洰褰曚笅鍒涘缓鐢ㄦ埛搴?
//璋冪敤鐢熸垚鐨?aardio 搴撹В鏋愬脊骞?import bilibili.community.service.dm.v1.DmSegMobileReply;
var dmSegMobileReply = bilibili.community.service.dm.v1.DmSegMobileReply();
dmSegMobileReply.parseFromString(content);

//鏄剧ず寮瑰箷
for(i=1;#dmSegMobileReply.elems){
    var elem = dmSegMobileReply.elems[i];
    console.log(elem.idStr,elem.content);
    //console.more(1000);
}

import web.json;

//涓嶉渶瑕佷换浣曞皝瑁咃紝鎵�鏈?Protobuf 娑堟伅瀵硅薄閮藉彲浠ョ洿鎺ヨ浆鎹负 json
var json = web.json.stringify(dmSegMobileReply);

//Protobuf 娑堟伅瀵硅薄鍙�氳繃 JSON 杞崲涓虹函 table 瀵硅薄
var tab = web.json.strip(dmSegMobileReply)

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/protobuf/QuickStart.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/protobuf/QuickStart.md')

