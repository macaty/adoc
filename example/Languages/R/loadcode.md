[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 R 璇█ - 宓屽叆妯℃澘

```aardio aardio
//aardio 璋冪敤 R 璇█ - 宓屽叆妯℃澘
import console.int;
import process.r;

//鎵ц R 浠ｇ爜锛屾敮鎸佹ā鏉胯娉曪細
//https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
var prcs = process.r.loadcode(`write("<?

//鍙互鍦?R 浠ｇ爜涓祵鍏?aardio  浠ｇ爜
if(_WIN10_LATER){
    print("鏂扮郴缁?,owner.妯℃澘鍙傛暟鍚?
}
else {
    print("鏃х郴缁?,owner.妯℃澘鍙傛暟鍚?
}

?>",file=".data.txt");`,{
    妯℃澘鍙傛暟鍚?= "鍙傛暟鍊?
})

prcs.logResponse();

console.log(string.load("/.data.txt"))

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/R/loadcode.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/R/loadcode.md')

