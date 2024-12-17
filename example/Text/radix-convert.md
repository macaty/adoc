[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 杩涘埗杞崲

```aardio aardio
//杩涘埗杞崲
//鐢ㄦ牸寮忓寲鍑芥暟鍙互瀹炵幇鏁板瓧鐨勮繘鍒惰浆鎹?//鍙傝�冩枃妗ｏ細 https://www.aardio.com/zh-cn/doc/library-guide/builtin/string/format.html

import console;

//鏁板瓧杞崲涓轰簩杩涘埗瀛楃涓?var str = string.format("%b",23 );
console.print(str);

//浜岃繘鍒跺瓧绗︿覆杞崲涓烘暟瀛?var n = tonumber(str,2);

//鏁板瓧杞崲涓哄叓杩涘埗瀛楃涓?str = string.format("%o",23 );
console.print(str);

//鍏繘鍒跺瓧绗︿覆杞崲涓烘暟瀛?n = tonumber(str,8);

//鏁板瓧杞崲涓哄崄鍏繘鍒跺瓧绗︿覆
str = string.format("%x",23 );
console.print(str);

//tostring 涔熷彲浠ョ敤鍙傛暟@2鎸囧畾鐨勮繘鍒惰浆鎹㈠弬鏁癅1鎸囧畾鐨勬暟鍊笺�?str = tostring(23,16);
console.print(str);

//鍗佸叚杩涘埗瀛楃涓茶浆鎹负鏁板瓧
n = tonumber(str,16);
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/radix-convert.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/radix-convert.md')

