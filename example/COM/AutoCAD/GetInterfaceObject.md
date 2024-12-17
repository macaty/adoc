[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 AutoCAD - 杩涚▼鍐呭璞?
```aardio aardio
//aardio 璋冪敤 AutoCAD - 杩涚▼鍐呭璞?import console
import com.cad;

var cad = com.cad();
cad.ShowForeground();

/*
涓婇潰鐨?cad 鏄繘绋嬪瀵硅薄( 涔熷氨鏄?ActiveX EXE)銆?浣嗘槸閫氳繃 cad.GetInterfaceObject(progId) 鍙互鍒涘缓 AutoCAD 杩涚▼鍐呭璞★紝
杩欏氨闈炲父鏈夎叮浜嗭紝涓嬮潰鐪嬩緥瀛愶細
*/

//鍦?AutoCAD 鍐呭垱寤?WSH 瀵硅薄
var wsh = cad.GetInterfaceObject("WScript.Shell")

//璁块棶 AutoCAD 杩涚▼鍐呯幆澧冨彉閲?var cadEnv = wsh.Environment("Process")

//淇敼 AutoCAD 杩涚▼鍐呯幆澧冨彉閲?cadEnv.setItem("aarEnvName","杩欐槸鍦?aardio 涓缃殑鐜鍙橀噺 ")

//璇诲彇 AutoCAD 杩涚▼鍐呯幆澧冨彉閲?var env = cadEnv.getItem("aarEnvName")

//AutoLISP 璇诲彇绗竴娆¤缃殑鐜鍙橀噺浠ュ悗浼间箮浼氱紦瀛橈紝鍐嶆淇敼鐜鍙橀噺鍙兘鏃犳晥銆?cad.SendCommand(`(getenv "aarEnvName")`);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/GetInterfaceObject.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/GetInterfaceObject.md')

