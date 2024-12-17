[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 请稍候正在打开网页......

```aardio aardio
//网页找图
import win.ui;
/*DSG{{*/
var winform = win.form(text="请稍候正在打开网页......";right=759;bottom=469)
winform.add()
/*}}*/

//导入浏览器控件支持库
import web.form;

//在winform上建立浏览器控件窗口
var wb = web.form( winform  );
wb.noScriptErr = true;

//打开网页
wb.go("http://bbs.aardio.com/forum-image-1.html");

//显示窗口
winform.show();

//等待指定HTML节点（匹配tagName,src等节点属性）
wb.waitQueryEles( tagName="img"; src="logo\.png" )
win.delay(1000);//给点时间让图像显示出�?
import soImage;//导入搜图扩展�?import inet.http;//导入HTTP支持�?
winform.text = "请稍�?正在下载样本数据"
var imgBytes = inet.http().get("http://bbs.aardio.com/static/image/common/logo.png");

//创建查找图像
var imgFind = soImage();
imgFind.setBytes( imgBytes,"*.png"); //解析下载的图像数据，注意要指定图像文件后缀�?imgFind.crop(29,33,193,55);//裁剪图像,尽可能去掉背景，保留特征最强的部分

/*
也可以使用下面的方法加载要查找的样本图像�?查找图像要尽可能的小，并尽可能裁剪去掉背景，突出查找特征�?img.load("/要查找的图片.bmp");
*/

/*
在窗口内查找图像
img.findImage(窗口句柄,x,y,x2,y2,step)
参数x,y,x2,y2指定要查找的范围，x、y为左上角坐标,x2、y2为右下角坐标�?step参数指定步进。除第一个参数以外，所有参数可选�?*/
var sm,x,y = imgFind.findImageInWindow(winform);
winform.text = "已找到图片，相似度：" + sm;

//移动鼠标
import mouse;
mouse.moveToWindow(x-50,y-50,winform.hwnd,8);//保留鼠标轨迹模仿真实的鼠标移�?mouse.click();//点击鼠标

//启动消息循环
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findImage.web.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Automation/ComputerVision/findImage.web.md')

