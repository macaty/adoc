[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍘嬬缉

```aardio aardio
//鍘嬬缉
import console;
import sevenZip.cmd;

console.open()
sevenZip.cmd.compress( "~/tools"
    ,"\test.7z"
    ,console.log //杩欓噷鍙互璁剧疆涓�涓洖璋冨嚱鏁?杈撳嚭鍥炴樉缁撴灉
    )
io.print("鍘嬬缉瀹屾垚")

sevenZip.cmd.extract( "\test.7z"
    ,"\test"
    ,console.log //杩欓噷鍙互璁剧疆涓�涓洖璋冨嚱鏁?杈撳嚭鍥炴樉缁撴灉
)
io.print("瑙ｅ帇瀹屾垚")

console.pause();
console.close();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zCompress.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/7Zip/7zCompress.md')

