[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: FFmpeg 入门

```aardio aardio
//FFmpeg 入门
import win.ui;
/*DSG{{*/
var winform = win.form(text="调用 FFmpeg";right=759;bottom=469)
winform.add(
edit={cls="edit";left=10;top=6;right=744;bottom=450;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import process.ffmpeg;

var ffmpeg = process.ffmpeg(,"-version");
winform.edit.text = ffmpeg.readAll();

//调用 ffmpeg.exe，FFmpeg参数用法: https://quickref.me/zh-CN/docs/ffmpeg.html
var ffmpeg = process.ffmpeg("/",//指定要处理的文件所在目�?    `-i "abc.m4a" -y -acodec libmp3lame -aq 0 "xyz.mp3"`);

//读取进程所有输出，不阻塞界面，但等待进程结束（阻塞代码向后执行�?winform.edit.text = ffmpeg.readAll();

/*
下面这样分开写参数也可以�?包含空格或存在需要转义字符的参数会自动在首尾加双引号并作转义处理�?*/
var ffmpeg = process.ffmpeg("/",
    "-i","abc.m4a","-y","-acodec","libmp3lame","-aq", "0","xyz.mp3");

//指定用文本框异步显示进程输出（不阻塞代码向后执行�?ffmpeg.logResponse(winform.edit);

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/FFmpeg/FFmpeg.md)

