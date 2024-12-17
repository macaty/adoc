[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 淇敼鏂囦欢鏉冮檺

```aardio aardio
//淇敼鏂囦欢鏉冮檺
import fsys;
import process.popen;
import sys.acl;

var path = io.fullpath( "/cacls.aardio" )

//绂佹鎵�鏈夋枃浠舵潈闄?绂佹鍒犻櫎
var prcs = process.popen("cacls.exe",path,"/P ",sys.acl.getUserName()+":n", "/C")
prcs.write('y\r\n');
prcs.close();

//鎭㈠瀹屽叏鎺у埗鏉冮檺
/*
var prcs = process.popen("cacls.exe",path,"/P","everyone:F","/C ")
prcs.write('y\r\n');
prcs.close();
*/

//浣跨敤鏍囧噯搴撴彁渚涚殑 fsys.acl 鍙互鏇寸畝娲佸湴鎵ц涓婇潰鐨勬搷浣滐紙鍙渷鐣ュ懡浠よ鍙傛暟锛夈�?//import fsys.acl;
//fsys.acl.cacls("/cacls.aardio"," /P everyone:F /C ");

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Permissions/cacls.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Permissions/cacls.md')

