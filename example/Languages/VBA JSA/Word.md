[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: //aardio 调用 VBA/JSA 操作 Word

```aardio aardio
////aardio 调用 VBA/JSA 操作 Word
//以下代码兼容 WPS JS
import console.int;
import com.doc;

var doc = com.doc( "/vba.docm" )
doc.Visible = true;

/*
�?Word �?WPS 中按 ALT + F11 打开代码窗口
�?VBA 里收到的是二维数组，不是交错数组（数组的数组�?
自由调用 VBA / JSA 函数，不需要确认启用宏�?*/
doc.vba.CreateTableWithStyle({
    {"标题1","标题2","标题3"},
    {"文字1","文字2","文字3"},
    {"文字5","文字5","文字6"},
})

//退�?//doc.Quit();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/VBA JSA/Word.md)

