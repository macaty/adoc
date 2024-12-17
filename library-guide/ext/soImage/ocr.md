[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 如何调用 soImage 快速识别简单验证码

## 一. 介绍

aardio 中提供了很多 OCR 组件可以用于识别验证码�?
soImage �?aardio 中常用的图像处理扩展库。使�?soImage 也可以实现简单的 OCR 功能。使�?soImage 的好处是简单且不需要第三方组件，soImage 的体积很小并支持生成独立 EXE 文件�?
注意 soImage 可用于识别简单验证码，复杂验证码请改用其他更大的 OCR 组件�?
## �? 使用简�?OCR 代码生成�?
�?aardio 的范例中提供了专门为 soImage 扩展库生成字库与 OCR 范例的工具：

[简�?OCR 生成器](../../../example/Automation/ComputerVision/soImage.ocr.html)

�?aardio 中运行上面的简�?OCR 生成器�?
1. 输入验证码图像下载网址�?2. 点击『获取下一个图像』按钮�?3. 首先人工识别并输入图像上的文本，并继续点击『获取下一个图像』按钮以生成自动识别图像的样本数据�?
该工具会自动生成识别验证码所需的字库样本与调用代码�?
## �? soImage 扩展库识别验证码示例

下面是一个使�?soImage 扩展库识别简单验证码的完�?aardio 代码示例�?
```aardio aardio
import soImage;
import inet.http;

//字库�?soImage 范例提供的工具自动生�?var ziku = {
"1":"11111111111111111111111111";
"2":"11111111000000110000001100";
"3":"11111110000000100000001000";
"4":"10000010100000101000001010";
"5":"11111110100000001000000010";
"6":"11111111100000011000000110";
"7":"11111110000000100000001000";
"8":"11111111100000111000001110";
"8":"11111111100000111000001110";
"9":"11111110100000101000001010";
"0":"11111111100000111000001110";
}

//创建图像对象
var img = soImage();

//下载图像
img.loadUrl("https://www.******.com/***.php")

//识别图像并返回文�?var text = img.ocr(ziku);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-guide/ext/soImage/ocr.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-guide/ext/soImage/ocr.md')

