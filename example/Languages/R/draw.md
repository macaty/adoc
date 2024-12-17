[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 R 璇█ - 绐楀彛缁樺浘

```aardio aardio
//aardio 璋冪敤 R 璇█ - 绐楀彛缁樺浘
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio 绐楀彛鏄剧ず R 缁樺浘";right=759;bottom=469;border="dialog frame";max=false;min=false)
winform.add(
button={cls="button";text="鐐硅繖閲岃皟鐢?R 缁樺浘";left=472;top=414;right=680;bottom=456;z=2};
plus={cls="plus";left=18;top=15;right=739;bottom=397;bgcolor=16777215;z=1}
)
/*}}*/

//R 璇█浠ｇ爜
var rCode = /*
draw_sine_wave <- function(filename, phase_shift = 0, amplitude = 1) {
  png(filename, width = 800, height = 600)
  x <- seq(0, 2 * pi, length.out = 1000)
  y <- amplitude * sin(x + phase_shift)

  # 缁樺埗鍥惧舰
  plot(x, y, type = "l", col = "blue", lwd = 2,
       main = paste("Dynamic Sine Wave, Amplitude:", round(amplitude, 2)),
       xlab = "X Axis", ylab = "Y Axis",
       xlim = c(0, 2 * pi), ylim = c(-2, 2))

  # 鍏抽棴璁惧
  dev.off()

  new_phase_shift <- phase_shift + pi / 20
  new_amplitude <- 1 + sin(phase_shift)

  return(list(phase_shift = new_phase_shift, amplitude = new_amplitude))
}
*/

import process.r;

//鍚姩 R
var r = process.r.startRpc(rCode);

winform.button.oncommand = function(id,event){

    //璁剧疆缁樺浘鍒濆鍙橀噺
    var params = {
        phase_shift = 0;
        amplitude = 1
    }

    //鍒涘缓瀹氭椂鍣?    winform.setInterval(
        function(){

            //璋冪敤 R 鍑芥暟
            params,err  = r.draw_sine_wave(io.fullpath("/test2.png"), params.phase_shift,params.amplitude)

            params = params.result;

            //鏄剧ず鍥惧儚锛屽厛璇诲彇鍒板唴瀛橈紝涓嶅崰鐢ㄦ枃浠讹紝璁?R 鍑芥暟鍙互鑷敱鍐欐枃浠躲�?            winform.plus.background = string.load("/test2.png");

        },80
    )

    winform.button.disabledText = {"鉁?;"鉁?;"鉁?;"鉁?;"鉁?;"鉁?}
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/R/draw.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/R/draw.md')

