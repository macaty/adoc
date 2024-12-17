[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵瑰鐞嗕笌 aardio 瀵规瘮 - for 鍛戒护涔嬫枃鏈垎鏋?
```aardio aardio
//鎵瑰鐞嗕笌 aardio 瀵规瘮 - for 鍛戒护涔嬫枃鏈垎鏋?import console
import process.batch;

//鎵瑰鐞?for 閬嶅巻骞舵媶鍒嗗瓧绗︿覆
var bat = process.batch(`
@echo off
for %%i in (abc,def,xyz) do echo %%i
`)
console.log(bat.read(-1))

/*
鐢╝ardio 瀹炵幇涓庝笂闈㈢浉鍚岀殑鍔熻兘,
寰幆閬嶅巻鐢ㄧ┖鏍奸敭銆佽烦鏍奸敭(tab)銆侀�楀彿銆佸垎鍙锋垨绛夊彿鎷嗗垎鍑烘潵鐨勫瓧绗︿覆锛?string.lines 鐨勭 @2 涓弬鏁版寚瀹氬垎闅旂锛屾敮鎸佺被姝ｅ垯琛ㄨ揪寮忕殑 aardio 妯″紡鍖归厤璇硶銆?*/
for( line in string.lines("abc,def,xyz","[\s,;=]") ){
    //娉ㄦ剰 aardio 閲屽惊鐜彉閲忓悕涓嶉渶瑕佸湪鍓嶉潰鍔?%锛屼篃涓嶉檺鍒跺彧鑳戒娇鐢?6涓瓧姣?    console.log(line)
}

//鍒涘缓娴嬭瘯鏂囦欢
string.save("/test.txt","abc,def
123,456" )

//鎵瑰鐞?for 閬嶅巻骞舵寜琛屾媶鍒嗗瓧绗︿覆
var bat = process.batch(`
@echo off
for /f "usebackq delims=, tokens=1,2" %%i in ("test.txt") do echo %%i,%%j
`)
//娉ㄦ剰鏂囦欢璺緞濡傛灉鏈夌┖鏍煎繀椤诲寘鍚湪寮曞彿鍐?//濡傛灉瑕佺敤寮曞彿鍖呭惈璺緞锛屽氨蹇呴』鍔犱笂 usebackq锛寀sebackq鐨勬剰鎬濇槸鐢ㄥ弽寮曞彿鍖呭惈鍛戒护锛屽崟寮曞彿鍖呭惈瀛楃涓诧紝鐒跺悗鍙屽紩鍙峰氨鍙互鍖呭惈鏂囦欢璺緞鑰屼笉鏄瓧绗︿覆浜?console.log(bat.read(-1));
console.more(1);

//aardio 闇�瑕佸厛璇绘枃浠跺埌瀛楃涓?var str = string.load("/test.txt")

//鍙傛暟@3鎸囧畾delims锛屽彲浠ョ敤寮哄ぇ鐨勬ā寮忓尮閰嶈娉曟寚瀹氬垎闅旂
for tokens in string.lines(str,,",") {
    //tokens鏄竴涓暟缁勶紝鍙互鐢?string.join 浠绘剰鎷兼帴鏁扮粍涓寚瀹氳寖鍥寸殑鍏冪礌瀹炵幇鎵瑰鐞?tokens=n-m 鐨勬晥鏋?    console.log(tokens[1],tokens[2])
}

/*
aardio 鎻愪緵浜嗗ぇ閲忕殑瀛楃涓插嚱鏁帮紝浠ュ強寮哄ぇ鐨勬ā寮忓尮閰嶅姛鑳斤紝
鍙互瀹炵幇闈炲父澶嶆潅鐨勬枃鏈В鏋愬姛鑳斤紝渚嬪鏍囧噯搴撲腑瑙ｆ瀽JSON鐨?web.json锛岃В鏋怷ML,HTML鐨?string.xml,string.html绛夌瓑
*/

//渚嬪鎴戜滑涔熷彲浠ョ敤 string.each 瀹炵幇涓婇潰鐨勫姛鑳?for a,b in string.each(str,"([^,]+),(.+)"){
    console.log(a,b)
}

//鍒犻櫎娴嬭瘯鏂囦欢
io.remove("/test.txt")
console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Bat/Bat aardio瀵规瘮/for.string.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Bat/Bat aardio瀵规瘮/for.string.md')

