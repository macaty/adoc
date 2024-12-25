[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 R 语言 - 窗口绘图

```aardio aardio
//aardio 调用 R 语言 - 窗口绘图
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio 窗口显示 R 绘图";right=759;bottom=469;border="dialog frame";max=false;min=false)
winform.add(
button={cls="button";text="点这里调�?R 绘图";left=472;top=414;right=680;bottom=456;z=2};
plus={cls="plus";left=18;top=15;right=739;bottom=397;bgcolor=16777215;z=1}
)
/*}}*/

//R 语言代码
var rCode = /*
draw_sine_wave <- function(filename, phase_shift = 0, amplitude = 1) {
  png(filename, width = 800, height = 600)
  x <- seq(0, 2 * pi, length.out = 1000)
  y <- amplitude * sin(x + phase_shift)

  # 绘制图形
  plot(x, y, type = "l", col = "blue", lwd = 2,
       main = paste("Dynamic Sine Wave, Amplitude:", round(amplitude, 2)),
       xlab = "X Axis", ylab = "Y Axis",
       xlim = c(0, 2 * pi), ylim = c(-2, 2))

  # 关闭设备
  dev.off()

  new_phase_shift <- phase_shift + pi / 20
  new_amplitude <- 1 + sin(phase_shift)

  return(list(phase_shift = new_phase_shift, amplitude = new_amplitude))
}
*/

import process.r;

//启动 R
var r = process.r.startRpc(rCode);

winform.button.oncommand = function(id,event){

    //设置绘图初始变量
    var params = {
        phase_shift = 0;
        amplitude = 1
    }

    //创建定时�?    winform.setInterval(
        function(){

            //调用 R 函数
            params,err  = r.draw_sine_wave(io.fullpath("/test2.png"), params.phase_shift,params.amplitude)

            params = params.result;

            //显示图像，先读取到内存，不占用文件，�?R 函数可以自由写文件�?            winform.plus.background = string.load("/test2.png");

        },80
    )

    winform.button.disabledText = {"�?;"�?;"�?;"�?;"�?;"�?}
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/R/draw.md)

