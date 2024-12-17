[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: sqlite 搴?- 鑾峰彇瀛楁鍚?
```aardio aardio
//sqlite 搴?- 鑾峰彇瀛楁鍚?import console;
import sqlite

var db = sqlite(":memory:");
db.exec( "CREATE TABLE film(title, length, year, starring);")

var cmd = db.prepare("SELECT * FROM [film] ")
var columns = cmd.getColumns();

//鏄剧ず鎵�鏈夊瓧娈靛悕
console.dump(columns);

//鑾峰彇鍏ㄩ儴鏁版嵁琛?var dataTable = cmd.getTable();

//杩欐牱涔熷彲浠ュ彇鍒版墍鏈夊瓧娈靛悕
console.dump(dataTable.fields);

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Database/sqlite/columns.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Database/sqlite/columns.md')

