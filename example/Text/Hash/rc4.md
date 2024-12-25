[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: RC4

```aardio aardio
//RC4
import console;
import crypt.rc4;

//RC4加密
var rc4 = crypt.rc4();
rc4.setPassword("Secret");
var ciphertext = rc4.encrypt("Attack at dawn") //加密
var hex = string.hex(ciphertext,"");//密文转换�?6进制

console.dump("加密结果(HEX)",hex);
console.dump("加密结果(BASE64)",crypt.encodeBin(ciphertext) );
console.log("与标准算法结果比较是否一致：",hex=="45A01F645FC35B383552544B9BF5");
console.log("解密",rc4.decrypt(ciphertext))

console.more(1)

var csp = crypt();
csp.setHashPassword("Secret",0x8003/*_CALG_MD5*/,0x6801/*_CALG_RC4*/,1/*_CRYPT_EXPORTABLE*/);
var ciphertext = csp.encrypt("Attack at dawn") //加密
var hex = string.hex(ciphertext,"");//密文转换�?6进制
console.log("哈希密钥加密结果(HEX)");
console.log("哈希密钥解密",csp.decrypt(ciphertext));
console.log(crypt.pem(csp.exportPlainTextKeyBlob().rgbKeyData,"RC4-MD5 KEY" ) )

execute("pause");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Hash/rc4.md)

