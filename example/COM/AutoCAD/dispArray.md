[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 AutoCAD - 瀵硅薄鏁扮粍

```aardio aardio
//aardio 璋冪敤 AutoCAD - 瀵硅薄鏁扮粍
import com.cad
var cad = com.cad();
cad.Visible = true;

var patternName = "ANSI31";//濉厖鍥炬鐨勫悕绉?var patternType = 0 ;// 濉厖绫诲瀷

//鍦ㄦā鍨嬬┖闂翠腑娣诲姞濉厖鍥炬瀵硅薄锛圚atch锛?var hatchObj = cad.ActiveDocument.ModelSpace.AddHatch(patternType, patternName, true);

//瀹氫箟鍦嗗績鍜屽崐寰?var centerPoint = {0;0;0};
var radius = 1;

//鍒涘缓鍦嗗璞?var circle = cad.ActiveDocument.ModelSpace.AddCircle(centerPoint, radius);

/*
濡傛灉鏁扮粍鎴愬憳涓烘櫘閫?COM 瀵硅薄锛圛Dispatch 瀵硅薄锛夛紝鍦?COM 鎺ュ彛涓嚜鍔ㄨ浆鎹负 VT_DISPATCH 绫诲瀷 SafeArray銆?缁嗚妭璇峰弬鑰冦�宎ardio 鑼冧緥 / COM 缁勪欢 / 杩涢樁鎻愮ず / 绫诲瀷杞崲瑙勫垯銆?*/
var outerLoop = { circle };

//娣诲姞涓�涓渾浣滀负濉厖鍥炬鐨勫寰幆杈圭晫
hatchObj.AppendOuterLoop (  outerLoop );

//璁＄畻骞舵洿鏂板～鍏呭浘妗?hatchObj.Evaluate();

//閲嶆柊鐢熸垚瑙嗗浘
cad.ActiveDocument.Regen(cad.acActiveViewport);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/dispArray.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/AutoCAD/dispArray.md')

