[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 澶氬瓧鑺傚瓧绗?
```aardio aardio
//澶氬瓧鑺傚瓧绗?import console;

var str = /**
鍙栧嚭鎵�鏈夌殑涓枃瀛楃
鍦ㄦā寮忓尮閰嶄腑,鍦嗙偣'.'琛ㄧず浠绘剰鍗曞瓧鑺傚瓧绗?鑰屽啋鍙?:'琛ㄧず浠绘剰澶氬瓧鑺傚瓧绗?渚嬪涓枃)
abcddddddddddddd杩欐槸涓�涓腑鏂囧瓧绗︿覆adfasdfasdf杩欏張鏄竴涓腑鏂囧瓧绗︿覆<a href="">杩欐槸瓒呴摼鎺ユ爣棰?/a>瀛楃涓?*/

for str in string.gmatch(str,':+') {
   console.log(str)
}
console.more(1);

console.log("鍙栧乏渚?涓眽瀛?,string.left(str,3,true) );
console.log("鍙栧彸渚?涓眽瀛?,string.right(str,3,true) );
console.log("鍙栫2鍒扮5涓眽瀛?,string.slice(str,2,5,true) );
console.more(1);

//灏嗕腑鏂囧瓧绗︿覆杞崲涓烘暟缁?var tab = string.split(str )
for(i=1;#tab;1){
    console.log( tab[i] ) //鏄剧ず绗琲涓瓧绗?}
console.more(1)

//杞崲涓篣niocde( UTF-16 )
var ustring = string.toUtf16(str);
for(i=1;#ustring / 2 ;1){ //UTF-16姣忎釜瀛楃涓插浐瀹氫负涓や釜瀛楄妭
    console.log( ustring[i],ustring[[i]] ) //涓嬫爣鎿嶄綔绗﹀彲浠ユ柟渚跨殑鏀寔Unicode鍙屽瓧鑺?}

//杞崲涓烘嫾闊?import string.conv.pinyin;
console.log( string.conv.pinyin("鏂板勾濂?) )
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/wchar.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/wchar.md')

