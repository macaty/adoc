[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: FFmpeg - 转换图像格式

```aardio aardio
//FFmpeg - 转换图像格式
import console.int;
import process.ffmpeg;

var ffmpeg = process.ffmpeg("/",
    "-y","-i","~/example/Graphics/.gdip.jpg","out.webp");

//指定用文本框异步显示进程输出（不阻塞代码向后执行�?ffmpeg.logResponse();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Media/FFmpeg/image.md)

