[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用腾讯�?API - 图像�?Excel

```aardio aardio
//调用腾讯�?API
import win.ui;
/*DSG{{*/
mainForm = win.form(text="调用腾讯�?API - 图像�?Excel";right=757;bottom=467)
mainForm.add(
btnConvert={cls="button";text="图像�?Excel";left=352;top=394;right=668;bottom=460;color=14120960;font=LOGFONT(h=-14);note="请先拖动一个或多个包含表格的图像到窗口";z=1};
edit={cls="edit";left=10;top=16;right=737;bottom=376;autohscroll=false;edge=1;multiline=1;vscroll=1;z=2}
)
/*}}*/

//存储待处理图像路�?var images = {};

//接受拖放
mainForm.onDropFiles = function(files){
    table.append(images,files);
    mainForm.edit.text = string.join(images,'\r\n');
}

//声明腾讯云接口，接口鉴权使用 v3 签名方法 TC3-HMAC-SHA256
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

//响应按钮事件，图像转 Excel
mainForm.btnConvert.oncommand = function(){

    mainForm.btnConvert.disabled = true;
    mainForm.edit.print();

    //遍历所有图�?    for(i,path in images){
        thread.delay(100);

        // Base64 编码
        var base64 = crypt.encodeBin(string.loadBuffer(path))

        //调用 API
        var result,err = ocrApi(ImageBase64 = base64);

        var resp = result[["Response"]];

        var data = resp[["Data"]];
        if(data){

            // Base64 解码
            var xls = crypt.decodeBin(data);

            //保存文件
            string.save(path+'.xlsx',xls )

            mainForm.edit.print(path + '.xlsx');
        }
        else {
            mainForm.edit.print(resp[["Error"]] || err);
        }

    }

    mainForm.btnConvert.disabled = false;

    //清空待处理图�?    images = {};
}

mainForm.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Web/REST/tencentCloud.md)

