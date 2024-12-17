[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: fsys.config

```aardio aardio
//fsys.config
import console;
import fsys.config;

//鍐欏叆閰嶇疆鏂囦欢
var cfgPath = io.appData("/aardio/test.fsys.config");
var cfg = fsys.config(cfgPath)
cfg.閰嶇疆鏂囦欢鍚?瀛楁鍚?= {
    a = 123;
    b = "瀛楃涓?
}

//璇诲彇閰嶇疆鏂囦欢
var cfgPath = io.appData("/aardio/test.fsys.config");
var cfg = fsys.config(cfgPath)
console.dumpJson( cfg.閰嶇疆鏂囦欢鍚?)

console.pause()

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Config/fsys.config.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Config/fsys.config.md')

