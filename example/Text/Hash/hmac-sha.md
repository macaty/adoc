[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HMAC-SHA

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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Hash/hmac-sha.md)

