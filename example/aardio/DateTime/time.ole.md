[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: OLE鏃堕棿瀵硅薄

```aardio aardio
//OLE鏃堕棿瀵硅薄

import console;
import time.ole;

//鎴戜滑璇曚竴涓嬪垱寤轰竴涓狾LE鏃堕棿瀵硅薄
var tm = time.ole();

//缁欎粬1970骞翠互鍓嶇殑鏃堕棿
tm.year = 1932;

//姝ｇ‘鍑虹幇鏁板�?console.log(  tonumber( tm )  )

tm.year = 3010;//骞?
//鍐嶆妸浠栬浆鎹㈠洖鏉?浠嶇劧姝ｇ‘鏄剧ず骞翠唤
console.log( time.ole( tonumber( tm ) ) )

//OLE鏃堕棿鏀寔绯荤粺鏍煎紡鍖栬娉?var str = tostring(tm,"yyyy-MM-dd HH:mm:ss")
console.dump(str)

//涔熼粯璁ゆ敮鎸乼ime瀵硅薄鐨勬牸寮忓寲璇硶
console.log(tostring(tm,"%Y骞?m鏈?d鏃?%H鏃?M鍒?S绉?))

//杩樺彲浠ヨ浆鎹㈡牸寮忓寲璇硶
console.log( tm.toSystemFormat("%Y骞?m鏈?d鏃?%H鏃?M鍒?S绉?))

//time瀵硅薄涔熸敮鎸?900骞村埌9999骞翠箣闂寸殑鏃堕棿
var tm = time("1969/1/1 11:21:03","%Y/%m/%d %H:%M:%S")
console.log(tm)

//浣嗘槸鏁板�艰繍琛屽氨涓嶆敮鎸佷簡
console.log( tonumber(tm) )

console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/time.ole.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/time.ole.md')

