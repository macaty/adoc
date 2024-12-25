[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 .NET 管理 IIS 服务�?
```aardio aardio
//aardio 调用 .NET 管理 IIS 服务�?import dotNet;

//�?IIS 自带的程序集导入 ServerManager 名字空间
if( ! dotNet.import("Microsoft.Web.Administration") ){
    error("您的系统没有安装 IIS 或缺�?Microsoft.Web.Administration.dll",2)
}

var serverManager = Microsoft.Web.Administration.ServerManager();
//启动指定网站
//注意 C# 中下标要改为 Sites.Item["www.aardio.com"]
serverManager.Sites.Item["www.aardio.com"].Start()

//注册 MIME
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

//下面这句取消注释，可用于提交更新�?//serverManager.CommitChanges();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/IIS.md)

