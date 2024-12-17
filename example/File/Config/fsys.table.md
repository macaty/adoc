[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: fsys.table

```aardio aardio
//fsys.table
import console;
import fsys.table;

var setting = fsys.table("/setting.table")
setting.load(); //浠庢枃浠惰浇鍏ヨ〃

//璇诲啓鎴愬憳,璞℃櫘閫歵able 瀵硅薄涓�鏍蜂娇鐢?setting.a = 123;
setting.b = 456;

//娣峰叆鎴愬憳鍒伴厤缃〃
setting.mixin(
    c = {a=1;b=2};
    d = 123;
    e = raw.buffer(5,"abc")
)

//淇濆瓨閰嶇疆琛?setting.save()

setting2 = fsys.table("/setting.table")
setting2.load(); //璇诲彇

for(k,v in setting2){
    console.log(k,v ) //璞℃櫘閫歵able瀵硅薄涓�鏍蜂娇鐢?}

console.log( setting2 ) //杞崲涓哄瓧绗︿覆

execute("pause")

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Config/fsys.table.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Config/fsys.table.md')

