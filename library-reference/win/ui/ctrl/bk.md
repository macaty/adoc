[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# win.ui.ctrl.bk 库模块帮助文�?
## win.ui.ctrl 成员列表

### win.ui.ctrl.bk()

无窗口控�?仅用于背景贴�?不建议用于频繁刷新绘�?
[返回对象:winuictrlbkObject](#winuictrlbkObject)

## winuictrlbkObject 成员列表

### winuictrlbkObject.background

参数指定图像路径，重设背景图�?

仅支持gif,jpg等，不支持png,

png贴图请改用bkplus控件

### winuictrlbkObject.bgcolor

背景�?RGB格式数�?
### winuictrlbkObject.forecolor

前景�?RGB格式数�?
### winuictrlbkObject.getPos（）

返回x,y,cx,cy,

x,y为控件坐�?cx,cy为控件宽、高

### winuictrlbkObject.linearGradient

线程渐变方向,0为水平方向，其他数值为垂直方向渐变

### winuictrlbkObject.onDrawBackground

```aardio aardio
winuictrlbkObject.onDrawBackground(hdc,rc){
    /*背景绘图以后触发此回�?
hdc为当前绘图设备句�?rc为控件位�?/
}

```

### winuictrlbkObject.redraw()

刷新,会导致背景窗口重建背景图缓存

不建议频繁调�?
### winuictrlbkObject.setBitmap()

参数指定位图句柄,重设背景位图

控件负责销毁位图句�?
[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/bk.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/ctrl/bk.md')

