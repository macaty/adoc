[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: XXTEA

```aardio aardio
//XXTEA
import console;
import crypt.bin;
import string.xxtea;

var plaintext = "娴嬭瘯鏄庢枃";
var password = "娴嬭瘯瀵嗙爜";

var ciphertext = string.xxtea.encrypt(plaintext,password ) ;
console.log("xxtea鍔犲瘑缁撴灉:",crypt.bin.encodeBase64(ciphertext) )

var plaintext = string.xxtea.decrypt(ciphertext,password) ;
console.log("xxtea瑙ｅ瘑缁撴灉:" ,plaintext  );

import web.rest.htmlClient;
var http = web.rest.htmlClient()

var htmlDoc  = http.api("https://www.tools4noobs.com/online_tools/").xxtea_encrypt(
    action="ajax_xxtea_encrypt";
    key=password;
    text=plaintext;
    encode="checked";
)

//鐢ㄥ湪绾垮伐鍏峰姣斾竴涓嬪姞瀵嗙粨鏋滄槸鍚︿竴鑷达細
if(htmlDoc) {
    console.log("xxtea鍦ㄧ嚎鍔犲瘑:", htmlDoc.getEle("resultx").innerText() );
}

console.pause("pause");

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Hash/xxtea.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Hash/xxtea.md')

