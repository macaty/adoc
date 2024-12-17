[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: com.smtp

```aardio aardio
//com.smtp
import console;
import com.smtp;

var smtp = com.smtp();

smtp.from="1000@qq.com" //鍙戜欢浜?smtp.to="1000@qq.com" //鏀朵欢浜?smtp.ssl = true;

smtp.server="smtp.qq.com" //閭欢鏈嶅姟鍣?smtp.username="1000@qq.com" //鐢ㄦ埛鍚?smtp.password = "1000100010001000" //瀵嗙爜
smtp.subject="鏍囬" //閭欢鏍囬
smtp.html="閭欢鍐呭" //閭欢鍐呭

io.open()
try{
    console.log("姝ｅ湪鍙戦�侀偖浠?..")
    smtp.send();//鍙戦�侀偖浠?}
catch(e){
    console.log("鍑洪敊浜?璇锋纭缃畇mtp鏈嶅姟鍣ㄧ櫥褰曚俊鎭?濡傚瘑鐮佺瓑.",e)
}

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/smtp/com.smtp.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/smtp/com.smtp.md')

