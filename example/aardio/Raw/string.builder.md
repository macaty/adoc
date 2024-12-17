[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瀛楃涓茬敓鎴愬櫒

```aardio aardio
//瀛楃涓茬敓鎴愬櫒
import console;
import string.builder;

//鍒涘缓瀛楃涓茬敓鎴愬櫒锛堝唴閮ㄥ熀浜庡姩鎬佹寚閽堬級
var bs = string.builder() //鍙彸閿偣 string.builder锛岀劧鍚庣偣銆岃烦杞埌瀹氫箟銆?
//璁剧疆鍒濆鍊?bs.assign("  鍒濆鍊?)

for(i=1;100;1){
    bs.append( tostring(i) );//杩藉姞瀛楃涓?    bs.appendf( "%d",i );
}

//娓呴櫎涓や晶绌烘牸
bs.trim()

//瀛楃涓叉搷浣滃嚱鏁?console.log("鍙充晶鍙?涓瓧绗? ,bs.rightString(3) );

//杞崲涓哄瓧绗︿覆
console.log("杞崲涓哄瓧绗︿覆" ,tostring(bs) );

console.log("棰勫垎閰嶅唴瀛樺ぇ灏?,bs.capacity())

console.log("瀹為檯瀛樺偍鍐呭澶у皬",bs.size())

//閲嶆柊璋冩暣瀛楃涓查暱搴?bs.resize(10)

//閲婃斁澶氫綑鐨勫唴瀛?bs.reserve(0);

//bs瀵硅薄鍦ㄤ笉浣跨敤鏃跺彲鑷姩閲婃斁锛屼絾涔熷彲浠ヤ富鍔ㄨ皟鐢╢ree()鍑芥暟灏介噺閲婃斁涓嶇敤鐨勫唴瀛?bs.free(); //鍦ㄩ噸鏂板垎閰嶅唴瀛樹箣鍓嶅氨涓嶈兘鍐嶈鍐欒鍐呭瓨浜?
if( ! bs.capacity() ){
    //浣嗘槸閲嶆柊鍒嗛厤鍐呭瓨鍙堝彲浠ョ敤浜?    bs.reserve(100);
}

bs += "閲嶆柊鍒嗛厤鍐呭瓨鍙堝彲浠ョ敤浜?;

console.log(bs)

console.log( bs.str() )

//鍙涓嬩笌缁撴瀯浣撹繛鎺?bs += {BYTE x[] ='dbcd\0'}
console.log( bs.toUtf16() )

console.pause(true);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Raw/string.builder.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Raw/string.builder.md')

