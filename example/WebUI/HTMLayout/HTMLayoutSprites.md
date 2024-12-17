[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 涔濆鏍煎姪鎵?
```aardio aardio
//涔濆鏍煎姪鎵?import process;
import sevenZip.decoder2.httpFile

var path = "~\download\tools\HTMLayout 涔濆鏍煎姪鎵?exe"
if(!io.exist(path)){
    sevenZip.decoder2.httpFile.download("http://download.aardio.com/aardio/ext/HTMLayout/HTMLayoutSprites.7z"
        ,"姝ｅ湪涓嬭浇涔濆鏍艰创鍥惧姪鎵?
        ,"~/download/tools/HTMLayoutSprites-temp","~/download/tools/"
    )

    import fsys;
    fsys.delete("~/download/tools/HTMLayoutSprites-temp/")
}

process.execute(path)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/HTMLayoutSprites.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/HTMLayoutSprites.md')

