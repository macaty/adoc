[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: gzip 璇诲啓

```aardio aardio
//gzip 璇诲啓

import zlib;

//鍒涘缓鍙啓gzip鏂囦欢
gz = zlib.gzFile("/璺緞.gz","wb")
gz.write( {
    int data=1234; //鍙互鍘嬬缉缁撴瀯浣?骞跺啓鍏zip鏂囦欢
    } )
gz.write("瀛楃涓?)//鍐欏叆瀛楃涓?gz.close();//鍏抽棴鏂囦欢鍙ユ焺

//鍒涘缓鍙gzip鏂囦欢
gz = zlib.gzFile("/璺緞.gz","rb")
var struct = gz.read( {
    int data=1234; //鍙互鑷猤zip鏂囦欢瑙ｅ帇璇诲彇缁撴瀯浣?    } )
var str = gz.read(-1) //瑙ｅ帇骞惰鍙栨墍鏈夊瓧绗︿覆
gz.close();//鍏抽棴鏂囦欢鍙ユ焺

io.open()
io.print( struct.data,str )
execute("pause")

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/Compression/gzfile.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/Compression/gzfile.md')

