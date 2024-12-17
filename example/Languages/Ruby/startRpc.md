[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Ruby 鍑芥暟

```aardio aardio
//璋冪敤 Ruby 鍑芥暟
import console.int;
import process.ruby;

var code  = /*

#鍙姞杞藉簲鐢ㄧ▼搴忕洰褰曚笅鐨勫叾浠栦唬鐮佹枃浠?#load "test.rb"

#瀹氫箟 Ruby 鍑芥暟
def add(a, b)
  a + b
end
*/

//鍚姩 Ruby RPC 鏈嶅姟绔紝杩欐牱灏变笉鐢ㄩ噸澶嶅惎鍔?Ruby锛岄�熷害鏇村揩
var ruby,err = process.ruby.startRpc( code )

//璋冪敤 Ruby 鍑芥暟
var ret,err  = ruby.add(2,3)

//鑾峰彇杩斿洖鍊?ret = ret[["result"]]
console.dump(ret);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/startRpc.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Ruby/startRpc.md')

