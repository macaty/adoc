[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 澶囩敤鏁版嵁娴?
```aardio aardio
//澶囩敤鏁版嵁娴?import console;
import sys.volume;

if(sys.volume.getInfo("/ads.aardio").fsys!="NTFS"){
    console.logPause("褰撳墠鍒嗗尯涓嶆槸 NTFS 鏂囦欢绯荤粺锛屼笉鏀寔鍛藉悕鏁版嵁娴併�?);
    return;
}

//鑷枃浠跺鐢ㄦ暟鎹祦璇诲彇澶囩敤鏁版嵁
var count = string.load("/ads.aardio:count")
count = (  count : 0 ) + 1;

//鍐欏叆鐪嬩笉瑙佺殑澶囩敤鏁版嵁娴?涔熷彲浠ュ彨鍛藉悕鏁版嵁娴?
string.save("/ads.aardio:count", count);

//鏄剧ず缁撴灉
console.log( "浣犲凡缁忚繍琛屼簡杩欎釜浠ｇ爜" +count+ "娆? );

import fsys.streamInfo;
var streamInfo = fsys.streamInfo("/ads.aardio")

//鏄剧ず鏂囦欢鐨勫叏閮ㄦ暟鎹祦鍚嶇О
console.dumpJson(streamInfo);
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/IO/ads.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/IO/ads.md')

