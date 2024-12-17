[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 屏幕找色

```aardio aardio
//屏幕找色
import gdi;
import win;
import mouse;
import soImage;
import winex;

//查找窗口
var hwndParent = winex.find("Afx\:\x+\:\x+\:\x+\:\x+\:\x+"," 副本");
var hwnd = winex.findEx(hwndParent,,"Afx\:RibbonBar\:\x+\:\x+\:\x+\:\x+","aardio ");
mouse.moveToWindow(0,0,hwnd);

//抓屏
var imgScreen = soImage();
imgScreen.captureWindow(hwnd);

//在图像上搜索指定颜色的点,
//第一个参数是一个表示查找颜色的数�?更多参数用法请查看智能提�?var x,y = imgScreen.findColor( gdi.RGB(48,171,53) );

//移动鼠标到指定位置，显示鼠标轨迹
mouse.moveToWindow(x,y,hwnd,8);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findColor.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findColor.md')

