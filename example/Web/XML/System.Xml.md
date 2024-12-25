[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: /XPath: System.Xml

```aardio aardio
///XPath: System.Xml
import console.int;
import dotNet;

//导入 .NET 名字空间（Win7 �?.NET 2.0 开始已经自�?System.Xml �?dotNet.import("System.Xml");

//文档: https://learn.microsoft.com/zh-cn/dotnet/api/system.xml.xmldocument?view=netframework-2.0
var xmlDoc = System.Xml.XmlDocument();

xmlDoc.LoadXml(`<?xml version="1.0" ?>
<国家 id="china">
    <省份>
        <省份详情 id="shanxi">陕西</省份详情>
        <地区>
            <�?id="xian">西安</�?
            <�?id="xianyang">咸阳</�?
        </地区>
    </省份>
    <省份>
        <省份详情 id="hunan">湖南</省份详情>
        <地区>
            <�?id="changsha">长沙</�?
            <�?id="zhuzhou">株洲</�?
        </地区>
    </省份>
</国家>`)

//XPath 查询
var ele = xmlDoc.SelectSingleNode(`//省份/省份详情[@id="shanxi"]`);
console.log(ele.OuterXml);

/*
XPath 语法速查
https://quickref.me/zh-CN/docs/xpath.html

`//省份/省份详情[@id="shanxi"]`
表示在『省份』下面去找『省份详情』，用斜杆分隔上下级关级�?两个 // 表示任意子级（忽略中间隔了多少层）�?最开始如果是单个 / 表示根节点�?
`省份详情[@id="shanxi"] `
表示『省份详情』必须有一�?id 属性，值为 "shanxi" �?属性名前面加一�?@ 符号�?*/

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/XML/System.Xml.md)

