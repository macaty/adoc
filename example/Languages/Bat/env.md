[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵瑰鐞嗕笌鐜鍙橀噺

```aardio aardio
//鎵瑰鐞嗕笌鐜鍙橀噺
//鐩稿叧鑼冧緥锛氳繘绋?> 绠￠亾
import win;
import process.popen

//鍦ㄧ埗杩涚▼涓寚瀹氱幆澧冨彉閲?string.setenv("TESTENV","娴嬭瘯鍙橀噺鍊?);

//涔熷彲浠ョ敤涓嬮潰鐨勬柟娉?//import environment
//environment.user().set("TESTENV","娴嬭瘯鍙橀噺鍊?)

//鎵撳紑鍛戒护琛?闅愯棌鍛戒护琛岀獥鍙?var prcs = process.popen.cmd(`echo %TESTENV%`)

//涔熷彲浠ュ湪 process 鎴?process.popen 鍙傛暟@3涓�氳繃 environment涓虹洰鏍囪繘绋嬫寚瀹氱幆澧冨彉閲?var prcs = process.popen("cmd.exe","/c echo %TESTENV2%",{
    environment = {
        TESTENV2 = "娴嬭瘯鍙橀噺鍊?"
    }
})

import fsys.environment;
import process.batch;
var prcs = process.batch( `
@echo off
set TESTENV3=娴嬭瘯鍙橀噺鍊?<?
    print( fsys.environment.expand("%appdata%") )

?>&
echo %TESTENV3%
`)

//鏄剧ず缁撴灉
import win;
win.msgbox(prcs.read(-1))

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Bat/env.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Bat/env.md')

