[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 简�?OCR 代码生成�?
```aardio aardio
//简�?OCR 生成�?import win.ui;
/*DSG{{*/
var winform = win.form(text="简�?OCR 代码生成�?;right=562;bottom=584)
winform.add(
btnNext={cls="button";text="获取下一个图�?;left=390;top=144;right=548;bottom=180;dr=1;dt=1;z=7};
editDict={cls="edit";left=12;top=238;right=548;bottom=571;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=4};
editText={cls="edit";left=151;top=145;right=362;bottom=177;dr=1;dt=1;edge=1;z=5};
editUrl={cls="edit";left=149;top=11;right=548;bottom=41;dl=1;dr=1;dt=1;edge=1;multiline=1;z=1};
plusImage={cls="plus";left=148;top=64;right=382;bottom=128;dr=1;dt=1;repeat="scale";z=3};
static={cls="static";text="图像下载网址�?;left=20;top=15;right=144;bottom=39;align="right";dt=1;transparent=1;z=2};
static2={cls="static";text="输入图像上的文本:";left=16;top=149;right=142;bottom=172;align="right";dr=1;dt=1;transparent=1;z=6};
static3={cls="static";text="字库与识别代码：";left=23;top=206;right=488;bottom=244;transparent=1;z=8}
)
/*}}*/

/*
这是一个不需要第三方组件的简�?OCR 实现，仅适用于识别规则数字�?请理解自行车里开不出航天飞机，复杂图文请改用其他 OCR 组件�?*/

import soImage;
import inet.http;
import util.table;

var imageDict = {};
var imageData;
winform.btnNext.oncommand = function(id,event){
    if(#imageData){
        var text = winform.editText.text;
        if(#text != #imageData ){
            winform.editText.showErrorTip("必须输入图像上的"+#imageData +"个字�?);
            return;
        }

        for(i=1;#imageData;1){
            imageDict[ text[[i]] ] = imageData[i];
        }

        import string.template;
        var strCode = string.template();
        strCode.template = /***
//字库
var dict = ${dict}

import win.ui;
/*DSG{{*/
var winform = win.form(text="OCR 示例";right=427;bottom=224)
winform.add(
edit={cls="edit";left=220;top=164;right=396;bottom=203;edge=1;z=2};
plus={cls="plus";left=27;top=17;right=398;bottom=121;z=1}
)
/*}}*/

import inet.http;
import soImage;

//下载图像
var img = soImage();
img.loadUrl("${url}");
winform.plus.background = img.getBytes("*.jpg");

//识别
winform.edit.text = img.ocr(dict);

winform.show();
win.loopMessage();
        ***/

        winform.editDict.text =  strCode.format(
            url = winform.editUrl.text;
            dict = ..util.table.stringify(imageDict,'\t');
        );
    }

    var img = soImage();
    if(! img.loadUrl(winform.editUrl.text) ){
        winform.editUrl.showWarningTip("获取图像失败，请指定正确网址�?);
        return;
    }

    winform.plusImage.background = img.getBytes("*.jpg")

    imageData = img.splitBinString();

    winform.editText.text = "";
    winform.editText.setFocus();
    winform.editText.showInfoTip("请输入验证码上的数字");
}

winform.editText.onOk = function(){
    winform.btnNext.oncommand();
    return true;
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/soImage.ocr.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/soImage.ocr.md')

