[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛鏄剧ず MATLAB 缁樺浘

```aardio aardio
//绐楀彛缁樺浘
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio 绐楀彛鏄剧ず MATLAB 缁樺浘";right=759;bottom=469;border="dialog frame";max=false;min=false)
winform.add(
button={cls="button";text="鐐硅繖閲岃皟鐢?MATLAB 缁樺浘";left=472;top=414;right=680;bottom=456;z=2};
plus={cls="plus";left=18;top=15;right=739;bottom=397;bgcolor=16777215;z=1}
)
/*}}*/

import com.matlab;
var m = com.matlab(true);

winform.button.oncommand = function(id,event){

    //璁剧疆缁樺浘鍙橀噺
    m.base.assign({
        filename = ..io.fullpath('/matlab.png');
        amplitude = 1;
        frequency = 1;
        phase = 0;
    });

    m.code = /******
    x = linspace(0, 2*pi, 100);
    y = amplitude * sin(frequency * x + phase);
    figure('Visible', 'off');

    plot(x, y, 'LineWidth', 2);
    title('Sine Wave');
    xlabel('X Axis');
    ylabel('Y Axis');
    grid on;

    set(gcf, 'Color', 'w');
    saveas(gcf, filename);
    close(gcf);
    ******/

     winform.plus.background = string.load("/matlab.png");
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/MATLAB/png.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/MATLAB/png.md')

