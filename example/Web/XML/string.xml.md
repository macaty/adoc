[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 简�?XML 解析

```aardio aardio
//简�?XML 解析
import string.xml;
import console;

var xmlstr =  /*
<?xml version="1.0" encoding="utf-8"?>
<project ver="10" name="aardio工程3" libEmbed="true" icon="...">
<file name="main" path="main.aardio" >
</file>
<folder name="资源文件" path="res" embed="true">
<![CDATA[
<folder name="资源文件" path="res" embed="true">
]]>
</folder>
<folder name="�? path="lib">
</folder>
<abc />
</project>
*/

xmlDoc = string.xml( xmlstr )

/*
上面的xmlDoc表示根节�?
xmlDoc包含一个所有子节点的数�?
例如 xmlDoc[1] 表示第一个子节点.

注意string.xml里返回的所有节点对象都是数组形式存在，
例如这里即使只有一个project节点，也要写xmlDoc.project[1]

�?xmlDoc.project[1] 为例，其所有子节点可以用数组索引如下访�?xmlDoc.project[1][1] 第一个子节点
xmlDoc.project[1][2] 第二个子节点

如果要找xmlDoc.project[1]下的forder节点，就要这样写
xmlDoc.project[1].folder[1] 第一个folder子节�?xmlDoc.project[1].folder[2] 第二个个folder子节�?*/

var project = xmlDoc.queryEles( tagName = "project");
for(index,tagName,childCount,xNode in project[1].eachChild() ){
    console.log( index,tagName,childCount,xNode.outerXml() )
}

/**
string.xml里一个节点对象是一个表,
这个节点对象如果有tagName属性表示标记名 - 那他就是一个普通节点�?如果没有tagName而是用text或cdata属�?- 那就说明他是一个text文本节点或者是cdata文本节点�?========================================
普通节点使�?tagName 属性表示XML标记�?
"tagName"属于保留�?其他属性使用此名字会被自动忽略�?根节点无tagName,注意这里的根节点指的是文档里的XML根节点的父节�?也就是总是虚拟出一个空的根节点�?
文本节点使用 text 属性表示文�?无tagName,无其他属�?CDATA节点使用 cdata 属性表示数�? 无tagName,无其他属�?
注释节点被自动忽略不会存为节点对�?xml声明节点的tagName�??xml"
**/

/*
string.xml 也可以用来解析HTML,
对于XML,HTML中的笔误等努力尝试修正为正确的结�?例如属性值为空或没放在引号中,标记忘记关闭,
忘记写开始标识不配对,或大小写首尾不匹�?- 关于大小写会首先尝试严格配对,配对不成功会检测是否笔误并进行修正 )

注意此支持库的作用是简单解�?校验XML错误等不是此支持库的目标,
所以只会尽可能的解析出能解析的结果,尽可能宽容错误写法并试图自动修正。如果需要比较严谨的XML解析�?- 请使用标准库中的 web.msxml
*/

console.pause()

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/XML/string.xml.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/XML/string.xml.md')
