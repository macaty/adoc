[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 入门

```aardio aardio
//入门
import console;
console.showLoading(" 正在下载 dm.proto");

import web.rest.github;
var proto = web.rest.github.getContent("SocialSisterYi/bilibili-API-collect/blob/master/grpc_api/bilibili/community/service/dm/v1/dm.proto")

import web.rest.client;
var http = web.rest.client();
var content = http.get("https://api.bilibili.com/x/v2/dm/web/seg.so",{
  "oid":"36570401","pid":"76459310","type":1,"segment_index":1
})

//解析 proto 生成 aardio �?import protobuf.parser;
protobuf.parser().parse(proto,,false);//去掉参数 @3 在工程目录下创建用户�?
//调用生成�?aardio 库解析弹�?import bilibili.community.service.dm.v1.DmSegMobileReply;
var dmSegMobileReply = bilibili.community.service.dm.v1.DmSegMobileReply();
dmSegMobileReply.parseFromString(content);

//显示弹幕
for(i=1;#dmSegMobileReply.elems){
    var elem = dmSegMobileReply.elems[i];
    console.log(elem.idStr,elem.content);
    //console.more(1000);
}

import web.json;

//不需要任何封装，所�?Protobuf 消息对象都可以直接转换为 json
var json = web.json.stringify(dmSegMobileReply);

//Protobuf 消息对象可通过 JSON 转换为纯 table 对象
var tab = web.json.strip(dmSegMobileReply)

console.pause(true);

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Network/protobuf/QuickStart.md)

