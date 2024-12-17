[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤鑵捐浜?API - 鍥惧儚杞?Excel

```aardio aardio
//璋冪敤鑵捐浜?API
import win.ui;
/*DSG{{*/
mainForm = win.form(text="璋冪敤鑵捐浜?API - 鍥惧儚杞?Excel";right=757;bottom=467)
mainForm.add(
btnConvert={cls="button";text="鍥惧儚杞?Excel";left=352;top=394;right=668;bottom=460;color=14120960;font=LOGFONT(h=-14);note="璇峰厛鎷栧姩涓�涓垨澶氫釜鍖呭惈琛ㄦ牸鐨勫浘鍍忓埌绐楀彛";z=1};
edit={cls="edit";left=10;top=16;right=737;bottom=376;autohscroll=false;edge=1;multiline=1;vscroll=1;z=2}
)
/*}}*/

//瀛樺偍寰呭鐞嗗浘鍍忚矾寰?var images = {};

//鎺ュ彈鎷栨斁
mainForm.onDropFiles = function(files){
    table.append(images,files);
    mainForm.edit.text = string.join(images,'\r\n');
}

//澹版槑鑵捐浜戞帴鍙ｏ紝鎺ュ彛閴存潈浣跨敤 v3 绛惧悕鏂规硶 TC3-HMAC-SHA256
import web.rest.tencentCloud;
var http = web.rest.tencentCloud(
    secretId = "secretId";
    secretKey = "secretKey";
    action =  "RecognizeTableAccurateOCR";
    version = "2018-11-19";
    region =  "ap-shanghai";
    service = "ocr";
);
var ocrApi = http.api("https://ocr.tencentcloudapi.com");

//鍝嶅簲鎸夐挳浜嬩欢锛屽浘鍍忚浆 Excel
mainForm.btnConvert.oncommand = function(){

    mainForm.btnConvert.disabled = true;
    mainForm.edit.print();

    //閬嶅巻鎵�鏈夊浘鍍?    for(i,path in images){
        thread.delay(100);

        // Base64 缂栫爜
        var base64 = crypt.encodeBin(string.loadBuffer(path))

        //璋冪敤 API
        var result,err = ocrApi(ImageBase64 = base64);

        var resp = result[["Response"]];

        var data = resp[["Data"]];
        if(data){

            // Base64 瑙ｇ爜
            var xls = crypt.decodeBin(data);

            //淇濆瓨鏂囦欢
            string.save(path+'.xlsx',xls )

            mainForm.edit.print(path + '.xlsx');
        }
        else {
            mainForm.edit.print(resp[["Error"]] || err);
        }

    }

    mainForm.btnConvert.disabled = false;

    //娓呯┖寰呭鐞嗗浘鍍?    images = {};
}

mainForm.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/tencentCloud.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/tencentCloud.md')

