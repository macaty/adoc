[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鍙戦�?Ctrl+C

```aardio aardio
//鍙戦�?Ctrl+C
import console
import process.popen

var prcs = process.popen("ping 127.0.0.1 -n 10 ")
for( all,out,err in prcs.each() ){
    console.log( out,err );
    prcs.ctrlEvent(0);
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Bat/ctrlEvent.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Bat/ctrlEvent.md')

