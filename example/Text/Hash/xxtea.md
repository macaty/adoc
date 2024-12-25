[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: XXTEA

```aardio aardio
//XXTEA
import console;
import crypt.bin;
import string.xxtea;

var plaintext = "测试明文";
var password = "测试密码";

var ciphertext = string.xxtea.encrypt(plaintext,password ) ;
console.log("xxtea加密结果:",crypt.bin.encodeBase64(ciphertext) )

var plaintext = string.xxtea.decrypt(ciphertext,password) ;
console.log("xxtea解密结果:" ,plaintext  );

import web.rest.htmlClient;
var http = web.rest.htmlClient()

var htmlDoc  = http.api("https://www.tools4noobs.com/online_tools/").xxtea_encrypt(
    action="ajax_xxtea_encrypt";
    key=password;
    text=plaintext;
    encode="checked";
)

//用在线工具对比一下加密结果是否一致：
if(htmlDoc) {
    console.log("xxtea在线加密:", htmlDoc.getEle("resultx").innerText() );
}

console.pause("pause");

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Hash/xxtea.md)

