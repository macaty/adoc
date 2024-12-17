[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 Python 妯″潡 matplotlib

```aardio aardio
//matplotlib
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio 璋冪敤 Python 妯″潡 matplotlib";right=759;bottom=469)
winform.add(
button={cls="button";text="璋冪敤 matplotlib 缁樺浘";left=440;top=399;right=632;bottom=455;color=14120960;db=1;dr=1;font=LOGFONT(h=-14);note="姣忔鐐瑰嚮閮戒細閲嶇粯涓�娆?;z=2};
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
plt.rcParams['font.sans-serif']=['SimHei'] #浣跨敤涓枃瀛椾綋
plt.rcParams['axes.unicode_minus']=False

def render():
    fig = plt.figure(figsize=(6, 6), dpi=300)
    ax = fig.add_subplot(111)
    x = np.random.randn(500)
    y = np.random.randn(500)

    ax.plot(x, y, '.', color='r', markersize=10, alpha=0.2)
    ax.set_title('matplotlib 娴嬭瘯')

    f = io.BytesIO()
    plt.savefig(f, dpi=fig.dpi)
    plt.close() #閲婃斁鍐呭瓨锛屼笉鐒跺唴瀛樹細涓�鐩村鍔?
    return f.getvalue()
**/
py3.exec( pyCode );//杩愯Python浠ｇ爜

winform.button.oncommand = function(id,event){

    //璋冪敤 Python 鍑芥暟
    var pyBytes = py3.main.render();

    //璁剧疆鍥惧儚锛屽弬鏁癅2涓?false 绂佹缂撳瓨鍥惧儚
    winform.plus.setBackground( pyBytes,false );
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/matplotlib.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/matplotlib.md')

