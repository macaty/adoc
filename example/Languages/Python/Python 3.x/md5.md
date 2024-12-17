[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Python 璁＄畻 MD5

```aardio aardio
//aardio 璋冪敤 Python 璁＄畻 MD5
import console;
import py3;

//瀵煎叆python妯″潡
var hashlib = py3.import("hashlib");

//鍒涘缓python瀵硅薄
var md5 = hashlib.md5()

//鍙傛暟涓簆ython涓殑bytes,鍦╝ardio瑕佷娇鐢╞uffer(瀛楄妭鏁扮粍)
md5.update( raw.buffer("娉ㄦ剰杩欎釜鍑芥暟鐨勫弬鏁颁笉鏄瓧绗︿覆鑰屾槸瀛楄妭鏁扮粍锛堢浉褰撲簬aardio涓殑buffer锛?) );

console.log( md5.hexdigest() );

import crypt;
console.log( crypt.md5("娉ㄦ剰杩欎釜鍑芥暟鐨勫弬鏁颁笉鏄瓧绗︿覆鑰屾槸瀛楄妭鏁扮粍锛堢浉褰撲簬aardio涓殑buffer锛?) )
console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/md5.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/md5.md')

