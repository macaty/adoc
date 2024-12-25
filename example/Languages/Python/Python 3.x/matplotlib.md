[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 调用 Python 模块 matplotlib

```aardio aardio
//matplotlib
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio 调用 Python 模块 matplotlib";right=759;bottom=469)
winform.add(
button={cls="button";text="调用 matplotlib 绘图";left=440;top=399;right=632;bottom=455;color=14120960;db=1;dr=1;font=LOGFONT(h=-14);note="每次点击都会重绘一�?;z=2};
plus={cls="plus";left=10;top=15;right=749;bottom=378;db=1;dl=1;dr=1;dt=1;repeat="scale";z=1}
)
/*}}*/

import py3;
import py3.lib.numpy;
import py3.lib.matplotlib;

var pyCode = /**
import io
import numpy as np
import matplotlib.pyplot as plt
plt.rcParams['font.sans-serif']=['SimHei'] #使用中文字体
plt.rcParams['axes.unicode_minus']=False

def render():
    fig = plt.figure(figsize=(6, 6), dpi=300)
    ax = fig.add_subplot(111)
    x = np.random.randn(500)
    y = np.random.randn(500)

    ax.plot(x, y, '.', color='r', markersize=10, alpha=0.2)
    ax.set_title('matplotlib 测试')

    f = io.BytesIO()
    plt.savefig(f, dpi=fig.dpi)
    plt.close() #释放内存，不然内存会一直增�?
    return f.getvalue()
**/
py3.exec( pyCode );//运行Python代码

winform.button.oncommand = function(id,event){

    //调用 Python 函数
    var pyBytes = py3.main.render();

    //设置图像，参数@2�?false 禁止缓存图像
    winform.plus.setBackground( pyBytes,false );
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/matplotlib.md)

