[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口显示 MATLAB 绘图

```aardio aardio
//窗口绘图
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio 窗口显示 MATLAB 绘图";right=759;bottom=469;border="dialog frame";max=false;min=false)
winform.add(
button={cls="button";text="点这里调�?MATLAB 绘图";left=472;top=414;right=680;bottom=456;z=2};
plus={cls="plus";left=18;top=15;right=739;bottom=397;bgcolor=16777215;z=1}
)
/*}}*/

import com.matlab;
var m = com.matlab(true);

winform.button.oncommand = function(id,event){

    //设置绘图变量
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/MATLAB/png.md)

