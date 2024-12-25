[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Base64

```aardio aardio
//Base64
import crypt.bin;
import console;

base64 = crypt.bin.encodeBase64( "base64编码可以将不可见的二进制字符串转换为可见的文本格�? );

console.log( "BASE64编码�?  , base64);
console.log( "BASE64解码�?  , crypt.bin.decodeBase64(base64) );

console.log( "BASE64解码（支持PEM，非BASE64文本）："  , crypt.decodeBin(base64)   );
console.log( crypt.pem("test","PEM") )

console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Hash/base64.md)

