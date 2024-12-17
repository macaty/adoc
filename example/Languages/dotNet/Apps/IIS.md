[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 .NET 绠＄悊 IIS 鏈嶅姟鍣?
```aardio aardio
//aardio 璋冪敤 .NET 绠＄悊 IIS 鏈嶅姟鍣?import dotNet;

//鑷?IIS 鑷甫鐨勭▼搴忛泦瀵煎叆 ServerManager 鍚嶅瓧绌洪棿
if( ! dotNet.import("Microsoft.Web.Administration") ){
    error("鎮ㄧ殑绯荤粺娌℃湁瀹夎 IIS 鎴栫己灏?Microsoft.Web.Administration.dll",2)
}

var serverManager = Microsoft.Web.Administration.ServerManager();
//鍚姩鎸囧畾缃戠珯
//娉ㄦ剰 C# 涓笅鏍囪鏀逛负 Sites.Item["www.aardio.com"]
serverManager.Sites.Item["www.aardio.com"].Start()

//娉ㄥ唽 MIME
/*
var config = serverManager.GetWebConfiguration("www.aardio.com");
var handlersSection = config.GetSection("system.webServer/handlers");

var handlersCollection = handlersSection.GetCollection();
var addElement = handlersCollection.CreateElement("add");
addElement.Item["name"] = "aardio";
addElement.Item["path"] = "*.aardio";
addElement.Item["verb"] = "*";
addElement.Item["modules"] = "FastCgiModule";
addElement.Item["scriptProcessor"] = "D:\aardioCGI\Publish\aardioCGI.exe";
handlersCollection.AddAt(0, addElement);
*/

//涓嬮潰杩欏彞鍙栨秷娉ㄩ噴锛屽彲鐢ㄤ簬鎻愪氦鏇存柊銆?//serverManager.CommitChanges();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/IIS.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/IIS.md')

