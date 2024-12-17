[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: HMAC-SHA

```aardio aardio
//HMAC-SHA
import console;
import crypt.bin;
import crypt.hmac;

key = '\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b\x0b';
data =  "Hi There";

//HMAC-SHA1
var hmacData = crypt.hmac.sha1(key,data).getValue();
hmacData = crypt.bin.encodeBase64( hmacData );
console.log( hmacData,#hmacData )

//HMAC-SHA256
var hmacData = crypt.hmac.sha256(key,data).getValue();
hmacData = crypt.bin.encodeBase64( hmacData );
console.log( hmacData,#hmacData )

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Hash/hmac-sha.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Hash/hmac-sha.md')

