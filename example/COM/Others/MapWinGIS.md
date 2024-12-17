[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 鎺ュ彛 - MapWinGIS

```aardio aardio
//COM 鎺ュ彛 - MapWinGIS
import win.ui;
/*DSG{{*/
var winform = win.form(text="MapWinGIS";right=759;bottom=469)
winform.add()
/*}}*/

var mapEmbed = winform.tryCreateEmbed("MAPWINGIS.Map.1")
if(!mapEmbed){
    import inet.installer;
    if( inet.installer("MapWinGIS"
        ,"https://github.com/MapWindow/MapWinGIS/releases/download/v5.2.4/MapWinGIS-only-v5.2.4-Win32-VS2017.exe"
        ,"/VERYSILENT /SUPPRESSMSGBOXES /NORESTART /NOICONS"
    ) ){
        mapEmbed = winform.tryCreateEmbed("MAPWINGIS.Map.1")
    }
}
if(!mapEmbed) return;

var axMap = mapEmbed._object
axMap.Projection = axMap.PROJECTION_GOOGLE_MERCATOR;
axMap.TileProvider = axMap.OpenStreetMap;
axMap.KnownExtents = axMap.keUSA;

axMap.Tiles.AutoDetectProxy(); //鑷姩鑾峰彇绯荤粺浠ｇ悊
//axMap.Tiles.SetProxy("ip_address_of_proxy", port); //鎸囧畾浠ｇ悊鏈嶅姟鍣?
//axMap.CursorMode = axMap.cmZoomIn; //鏀惧ぇ
//axMap.CursorMode = axMap.cmZoomOut; //缂╁皬
//axMap.CursorMode = axMap.cmPan; //婕父
//axMap.ZoomToMaxExtents(); //鍏ㄥ箙

//娴嬮噺
axMap.CursorMode = axMap.cmMeasure;
axMap.Measuring.MeasuringType= axMap.MeasureArea;

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Others/MapWinGIS.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Others/MapWinGIS.md')

