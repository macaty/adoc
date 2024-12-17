[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鏃堕棿鎴?
```aardio aardio
//鏃堕棿鎴?//Unix 鏃堕棿鎴?0 琛ㄧず ISO8601 鏃堕棿 1970-01-01T00:00:00Z
import console.int;
import fsys.time;

//Unix 鏃堕棿鎴筹紝杩斿洖鏁板�硷紝浠ユ绉掍负鍗曚綅
var stamp = time.stamp();
console.log(stamp);

//Unix 鏃堕棿鎴筹紝杩斿洖瀛楃涓诧紝浠ユ绉掍负鍗曚綅
var stamp = time.stamp(true);
console.log(stamp);

//Unix 鏃堕棿鎴筹紝杩斿洖瀛楃涓诧紝浠ョ涓哄崟浣?var stamp = time.stamp(true,1);
console.log(stamp);

//Unix 鏃堕棿鎴筹紝浠ョ涓哄崟浣?var stamp = tonumber( time() );
console.log(stamp);

//Unix 鏃堕棿鎴筹紝杩斿洖瀛楃涓诧紝浠ユ绉掍负鍗曚綅
var fileTime = fsys.time().now();
var stamp = fileTime.stamp(true);
console.log(stamp);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/timestamp.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/DateTime/timestamp.md')

