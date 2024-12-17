[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 缃戠粶鍥惧儚/瑁佸壀

```aardio aardio
//缃戠粶鍥惧儚/瑁佸壀
import gdip.bitmap;
import inet.http;//瀵煎叆姝ゅ簱鍙敮鎸佺綉缁滃浘鍍?
//澶氱嚎绋嬪姞杞界綉缁滃浘鍍忥紝鍦ㄧ獥鍙ｇ▼搴忎腑涔熶笉浼氬崱鐣岄潰
var bitmap = gdip.bitmap( "https://鍏堟妸杩欓噷鏀逛负鏈夋晥鍦板潃濂藉悧" )
var bitmapNew = bitmap.clone(65,20,120,50)

/*
var bitmapNew = gdip.bitmap(50,50);
bitmapNew.graphics.drawImageRectRect(bitmap,0,0,50,50,30,30,50,50)
*/

//bitmapNew.save("/testHttp.jpg")

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Graphics/http.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Graphics/http.md')

