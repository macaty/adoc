[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Go 璇█ - 璋冪敤 COM 鎺ュ彛 DLL

```aardio aardio
//aardio 璋冪敤 Go 璇█ - 璋冪敤 COM 鎺ュ彛 DLL
import console.int;
console.open();

//鍐呭瓨鍔犺浇 DLL锛岃鍏堢紪璇?Go 浠ｇ爜鐢熸垚 DLL
var dll = raw.loadDll($"/dispDemo.dll",,"cdecl");

//aardio 瀵硅薄杞崲涓?COM 瀵硅薄锛圕OM 鎺ュ彛浼氳嚜鍔ㄨ浆鎹紝鍘熺敓 DLL 鎺ュ彛瑕佽皟鐢?com.ImplInterface 锛?import com;
var disp = com.ImplInterface(
    //浠绘剰琛ㄥ璞℃垨鍑芥暟閮藉彲浠ヨ浆鎹负 COM 瀵硅薄锛圛Dispatch 鎺ュ彛瀵硅薄锛?    Add = function(a,b){

        console.log("Add 鍑芥暟琚?Go 璇█璋冪敤浜?);
        return a + b;
    }
);

//璋冪敤 Go 鍑芥暟
var pDisp = dll.TestDispatchP(disp);

//灏?Go 鍑芥暟杩斿洖鐨?IDispatch 鎸囬拡杞崲涓?COM 瀵硅薄
var comObj = com.QueryObjectR(pDisp);//杞崲鍚屾椂閲婃斁涓�娆″紩鐢ㄨ鏁?
//鎿嶄綔 COM 瀵硅薄
comObj.Add("key","value");
comObj.Add("key2","value2");

//閬嶅巻 COM 瀵硅薄
for index,key in com.each(comObj) {
    //杈撳嚭瀛楀吀鐨勯敭鍊?    console.log( key,comObj.Item(key) )
}

console.log(ptr)

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Go/COM Interface/disp-call.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Go/COM Interface/disp-call.md')

