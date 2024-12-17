[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RC4

```aardio aardio
//RC4
import console;
import crypt.rc4;

//RC4鍔犲瘑
var rc4 = crypt.rc4();
rc4.setPassword("Secret");
var ciphertext = rc4.encrypt("Attack at dawn") //鍔犲瘑
var hex = string.hex(ciphertext,"");//瀵嗘枃杞崲涓?6杩涘埗

console.dump("鍔犲瘑缁撴灉(HEX)",hex);
console.dump("鍔犲瘑缁撴灉(BASE64)",crypt.encodeBin(ciphertext) );
console.log("涓庢爣鍑嗙畻娉曠粨鏋滄瘮杈冩槸鍚︿竴鑷达細",hex=="45A01F645FC35B383552544B9BF5");
console.log("瑙ｅ瘑",rc4.decrypt(ciphertext))

console.more(1)

var csp = crypt();
csp.setHashPassword("Secret",0x8003/*_CALG_MD5*/,0x6801/*_CALG_RC4*/,1/*_CRYPT_EXPORTABLE*/);
var ciphertext = csp.encrypt("Attack at dawn") //鍔犲瘑
var hex = string.hex(ciphertext,"");//瀵嗘枃杞崲涓?6杩涘埗
console.log("鍝堝笇瀵嗛挜鍔犲瘑缁撴灉(HEX)");
console.log("鍝堝笇瀵嗛挜瑙ｅ瘑",csp.decrypt(ciphertext));
console.log(crypt.pem(csp.exportPlainTextKeyBlob().rgbKeyData,"RC4-MD5 KEY" ) )

execute("pause");

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Hash/rc4.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Hash/rc4.md')

