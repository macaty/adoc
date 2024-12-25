[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 九宫格助�?
```aardio aardio
//九宫格助�?import process;
import sevenZip.decoder2.httpFile

var path = "~\download\tools\HTMLayout 九宫格助�?exe"
if(!io.exist(path)){
    sevenZip.decoder2.httpFile.download("http://download.aardio.com/aardio/ext/HTMLayout/HTMLayoutSprites.7z"
        ,"正在下载九宫格贴图助�?
        ,"~/download/tools/HTMLayoutSprites-temp","~/download/tools/"
    )

    import fsys;
    fsys.delete("~/download/tools/HTMLayoutSprites-temp/")
}

process.execute(path)

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/HTMLayoutSprites.md)

