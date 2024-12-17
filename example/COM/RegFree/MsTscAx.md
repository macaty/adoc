[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 鎺ュ彛 - 鍏嶆敞鍐岃皟鐢ㄨ繙绋嬫闈㈡帶浠?
```aardio aardio
//COM 鎺ュ彛 - 鍏嶆敞鍐岃皟鐢ㄨ繙绋嬫闈㈡帶浠?import win.ui;
/*DSG{{*/
var winform = win.form(text="杩滅▼妗岄潰瀹㈡埛绔?;right=599;bottom=799)
winform.add()
/*}}*/

winform.onEraseBkgnd = lambda() 0;
winform.show();

import com.lite;
var dll = com.lite("MsTscAx.dll");

//濡傛灉涓嶆槸鍐呭瓨 DLL 鍙互鐪佺暐鍙傛暟@2閲屾寚瀹氱殑绫诲悕( aardio 浼氳嚜鍔ㄨ幏鍙?
var tsc = dll.createEmbedEx(winform,"{7cacbd7b-0d99-468f-ac33-22e495c0afe5}")

//鍝嶅簲杩滅▼妗岄潰浜嬩欢,鎺т欢瀹瑰櫒瀵硅薄鏄粯璁ょ殑浜嬩欢鐩戝惉瀵硅薄
tsc.OnDisconnected = function(discReason){
    select (discReason)  {
        case 2{
            winform.msgbox("宸叉敞閿�鐧诲綍");
        }
        else{
            winform.msgbox("杩滅▼杩炴帴澶辫触");
        }
    }
}

//璁剧疆杩滅▼鐧诲綍鍙傛暟 https://docs.microsoft.com/en-us/windows/win32/termserv/mstscax
tsc.Server = "鏈嶅姟鍣ㄥ湴鍧�";
tsc.UserName = "鐧诲綍鐢ㄦ埛鍚?;
tsc.AdvancedSettings2.ClearTextPassword = "鐧诲綍瀵嗙爜"; //淇濆瓨瀵嗙爜鍙渷鐣?tsc.AdvancedSettings2.EnableCredSspSupport = true; //鍚敤鍑嵁瀹夊叏鏈嶅姟鎻愪緵绋嬪簭(CredSSP)

tsc.AdvancedSettings2.RDPPort = 3389; //绔彛
tsc.AdvancedSettings2.RedirectPrinters = false; //鍙栨秷鍏变韩鎵撳嵃
tsc.AdvancedSettings2.RedirectDrives = true; //鍏佽鍏变韩纾佺洏
tsc.AdvancedSettings2.SmartSizing = true; //鑷姩璋冩暣澶у皬
tsc.DesktopWidth = "800" //妗岄潰瀹藉害
tsc.DesktopHeight = "600"; //妗岄潰楂樺害
tsc.FullScreen = false;//鏄惁鍏ㄥ睆
tsc.FullScreenTitle = winform.text;//鍏ㄥ睆鏍囬
tsc.ColorDepth = 32;//32浣嶉鑹?tsc.ConnectingText = "姝ｅ湪杩炴帴......"
tsc.Connect(); //杩炴帴

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/RegFree/MsTscAx.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/RegFree/MsTscAx.md')

