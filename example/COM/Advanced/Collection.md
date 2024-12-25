[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: COM 接口 - 修改集合�?
```aardio aardio
//COM 接口 - 修改集合�?import console.int;
import com.doc;

var docx = com.doc("/test.docx")
docx.Visible = true;

//�?set 前缀修改集合值（带参数属性）
docx.ActiveDocument.setBuiltinDocumentProperties("Title", "新标�?);

//这个 value 比较特别，直接写属性会报错（需�?DocumentProperty 类型 �?//docx.ActiveDocument.BuiltinDocumentProperties("Title").value = "新标�?;

//读属性可直接返回字符串，�?getBuiltinDocumentProperties("Title") 返回的又�?DocumentProperty
var title = docx.ActiveDocument.BuiltinDocumentProperties("Title").value;
console.log("新标�? " ,title );

docx.Save();
docx.quit();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/Advanced/Collection.md)

