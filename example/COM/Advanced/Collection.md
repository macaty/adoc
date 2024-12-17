[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 鎺ュ彛 - 淇敼闆嗗悎鍊?
```aardio aardio
//COM 鎺ュ彛 - 淇敼闆嗗悎鍊?import console.int;
import com.doc;

var docx = com.doc("/test.docx")
docx.Visible = true;

//鍔?set 鍓嶇紑淇敼闆嗗悎鍊硷紙甯﹀弬鏁板睘鎬э級
docx.ActiveDocument.setBuiltinDocumentProperties("Title", "鏂版爣棰?);

//杩欎釜 value 姣旇緝鐗瑰埆锛岀洿鎺ュ啓灞炴�т細鎶ラ敊锛堥渶瑕?DocumentProperty 绫诲瀷 锛?//docx.ActiveDocument.BuiltinDocumentProperties("Title").value = "鏂版爣棰?;

//璇诲睘鎬у彲鐩存帴杩斿洖瀛楃涓诧紝浣?getBuiltinDocumentProperties("Title") 杩斿洖鐨勫張鏄?DocumentProperty
var title = docx.ActiveDocument.BuiltinDocumentProperties("Title").value;
console.log("鏂版爣棰? " ,title );

docx.Save();
docx.quit();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Advanced/Collection.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Advanced/Collection.md')

