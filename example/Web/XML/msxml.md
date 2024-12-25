[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: MSXML 读写

```aardio aardio
//MSXML 读写

import console;
import web.msxml

xmlstr =/*<?xml version="1.0" encoding="utf-8"?>
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
</国家>*/

//解析 XML
var xmlDoc = web.msxml(xmlstr);

//可转换为字符串，下面代码等价�?console.log( tostring(xmlDoc.xml) );
console.log( xmlDoc.xml );

//XPath 查询
var eles = xmlDoc.selectNodes("/国家/省份[2]/地区[1]/市[1]");
//XPath 语法速查: https://quickref.me/zh-CN/docs/xpath.html

//长度
console.log("XPath返回数组长度",eles.length)
console.log("XPath返回节点文本",eles[0].text)

//按条件查询节�?qNodes = xmlDoc.queryNodes( tagName="�?;text ="西安" )
console.log( qNodes.text );

//eachNode() 参数一可选指定tagName,参数二可选指定父节点
for(k,xnode in xmlDoc.eachNode( "省份") ){
    for(k,xnode in xmlDoc.eachNode( "省份详情",xnode) ){
        console.log( "省份详情 Id: " ,  xnode.attributes(0).nodeValue  );
        console.log( "省份详情 value: " ,xnode.text  );
    }
    for(k,xnode in xmlDoc.eachNode( "地区",xnode ) ){
        for(k,xnode in xmlDoc.eachNode( "�?,xnode ) ){
            console.log( "   �?Id: ", xnode.attributes(0).nodeValue );
            console.log( "   �?value: ", xnode.text );
        }
    }
}

var root = xmlDoc.documentElement

//修改国家下属第一个字节点的文本内�?//注意 aardio数组下标�?开�?而com数组下标从零开�?//下面两句的作用是一样的
root.childNodes(0).Text="testitem"

//COM 对象可在属性名字前加上set前缀、并以函数形式调用属性方�?root.childNodes(0).setText("testitem2")

//下面这几句作用是一样的
var text = root.childNodes(0).Text;
var text = root.childNodes(0).getText() //在属性名字前加上get前缀、并以函数形式调用属性方�?var text = root.childNodes.item(0).getText()
console.log( text)

//更简单的方法
console.log( xmlDoc.�?0).text  );

//保存xml文件
xmlDoc.save( "/result.xmlDoc" )

import process;
process.execute("notepad.exe",xmlDoc.url )

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/XML/msxml.md)

