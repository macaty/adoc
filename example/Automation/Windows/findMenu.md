[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛鑷姩鍖?- 鎿嶄綔绐楀彛鑿滃崟

```aardio aardio
//绐楀彛鑷姩鍖?- 鎿嶄綔绐楀彛鑿滃崟
import winex;
import process;
import win.version;

error("浠ｇ爜浠呴�傜敤浼犵粺绐楀彛鑿滃崟锛學in11 璁颁簨鏈凡鏀圭増");

var prcs = process("Notepad");
var hwnd = winex.find("Notepad",,prcs.id);
var hEdit = winex.findEx(hwnd,1,"Edit");
winex.sendString("test",hEdit);

//鏌ユ壘鎸囧畾鐨勮彍鍗? "鏂囦欢" 鑿滃崟涓嬬殑 "鍙﹀瓨涓? )
//var hMenu,menuId = winex.findMenu(hwnd ,"鏂囦欢","鍙﹀瓨涓?);
//winex.click(hwnd,menuId);

//鐐瑰嚮鑿滃崟椤? "鏂囦欢" 鑿滃崟涓嬬殑 "鍙﹀瓨涓? )
winex.click( hwnd,"鏂囦欢","鍙﹀瓨涓?)

/*
娉ㄦ剰杩欑鏂瑰紡浠呯敤浜庣偣鍑讳紶缁熺獥鍙ｈ彍鍗曪紝
鏃犲彞鏌勮彍鍗曡鏀圭敤 string.ocrLite 鎴?dotNet.ocr 绛夊睆骞曟壘瀛楃粍浠躲�?*/

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/Windows/findMenu.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/Windows/findMenu.md')

