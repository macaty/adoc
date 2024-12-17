[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: ID3 鏍囩

```aardio aardio
//ID3 鏍囩
import console;
import fsys.tagLib;
import fsys.dlg;

var mp3Path = fsys.dlg.open("*.mp3|*.mp3");
if(!mp3Path) return;

var tagFile = fsys.tagLib(mp3Path);
console.dumpJson(tagFile);

for name,value in tagFile.each(){
    console.log(name,value);
}

console.log(tagFile.title);
console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/ID3.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/ID3.md')

