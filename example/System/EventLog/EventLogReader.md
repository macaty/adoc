[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏌ヨ鑷畾涔夋棩蹇?
```aardio aardio
//鏌ヨ鑷畾涔夋棩蹇?//鐩稿叧鑼冧緥: ~\codes\鑼冧緥绋嬪簭\9) 缃戠粶搴旂敤\0) 缃戠粶绠＄悊\6) wlanEnumInterfaces.aardio

import console.int;
import System.Diagnostics.Eventing;

//鏌ヨ鏉′欢
var query = System.Diagnostics.Eventing.Reader.EventLogQuery("Microsoft-Windows-NetworkProfile/Operational",1)
query.ReverseDirection = true;//璁剧疆鏌ヨ鏂瑰悜涓轰粠鏈�鏂板埌鏈�鏃?
//璇绘棩蹇楀璞?var logReader = System.Diagnostics.Eventing.Reader.EventLogReader(query);

//閬嶅巻浜嬩欢璁板綍
while( var eventInstance = logReader.ReadEvent() ) {

    //鑱旂綉浜嬩欢
    if(eventInstance.Id==10000
        || eventInstance.Id==10001){

        console.log( eventInstance.TimeCreated ,eventInstance.Id  )
        console.log( eventInstance.FormatDescription() )
        console.more(1)
    }
}

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/EventLog/EventLogReader.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/EventLog/EventLogReader.md')

