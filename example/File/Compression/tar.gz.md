[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: tar.gz 鍘嬬缉瑙ｅ帇

```aardio aardio
//tar.gz 鍘嬬缉瑙ｅ帇

import console;
import fsys.tar;
import fsys.untar;

//tar 鎵撳寘
var tarFile = fsys.tar("/test.tar.gz");
tarFile.onWriteFile = function( filename ){
        console.log("宸叉墦鍖?,filename)
}
tarFile.pack("~/lib/fsys/")
tarFile.close(); //鍏抽棴骞堕噴鏀炬枃浠?
//tar 瑙ｅ寘
var tar = fsys.untar( "/test.tar.gz","/瑙ｅ帇鐩綍" );
for(fileName,writeSize,remainSize in tar.eachBlock() ){
    console.printf("姝ｅ湪瑙ｅ帇锛?s 瀛楄妭鏁帮細%d",fileName,writeSize  )
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Compression/tar.gz.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Compression/tar.gz.md')

