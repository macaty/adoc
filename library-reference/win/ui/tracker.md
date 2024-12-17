[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# win.ui.tracker 库模块帮助文�?
## win.ui 成员列表

### win.ui.tracker

创建鼠标跟踪�?

### win.ui.tracker()

[返回对象:winUiTrackerObject](#winUiTrackerObject)

### win.ui.tracker(控件对象)

参数为控件或窗口对象

返回鼠标跟踪�?\- 实际上就是返回控件对象自�?

如果已经调用此函数创建过鼠标跟踪�?则直接返回参�?
## winUiTrackerObject 成员列表

### winUiTrackerObject.focusOnClick

设为false时禁止在单击控件时设置此控件为焦点控�?
### winUiTrackerObject.onFocusGot(hLostFocus)

```aardio aardio
winUiTrackerObject.onFocusGot = function(hLostFocus){
    ..win.setFocus(hLostFocus);/*得到焦点触发此事�?hLostFocus为失去焦点的窗口句柄,
如果在这里将hLostFocus恢复焦点,则阻止当前窗口得到焦�?/
}

```

### winUiTrackerObject.onFocusLost(hFocus)

```aardio aardio
winUiTrackerObject.onFocusLost = function(hFocus){
    /*失去焦点触发此事�?hFocus为得到焦点的窗口句柄*/
}

```

### winUiTrackerObject.onKeyDown

```aardio aardio
winUiTrackerObject.onKeyDown = function(keyCode,lParam,repeat){
    /*按下键盘�?/
}

```

### winUiTrackerObject.onKeyUp

```aardio aardio
winUiTrackerObject.onKeyUp = function(keyCode,lParam){
    /*放开键盘�?/
}

```

### winUiTrackerObject.onMouseActivate

```aardio aardio
winUiTrackerObject.onMouseActivate = function(hwndTop,hitTest,message){
    return _MA_/*鼠标点击并且将要激活窗口时触发此事�?hwndTop表示被激活的顶层窗口,
hitTest参数请参考WM_NCHITTEST消息
message为鼠标消息ID
返回值的作用请参数MSDN*/
}

```

### winUiTrackerObject.onMouseClick

```aardio aardio
winUiTrackerObject.onMouseClick = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键在控件上单击,
orphanWindow模式下如果阻止控件得到焦�?此事件不会被触发*/
}

```

### winUiTrackerObject.onMouseDoubleClick

```aardio aardio
winUiTrackerObject.onMouseDoubleClick = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标双击*/
}

```

### winUiTrackerObject.onMouseDown

```aardio aardio
winUiTrackerObject.onMouseDown = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键按下,
orphanWindow模式下如果阻止控件得到焦�?此事件不会被触发*/
}

```

### winUiTrackerObject.onMouseDrag

```aardio aardio
winUiTrackerObject.onMouseDrag = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键按下拖动,
自动捕获鼠标,允许拖出控件范围*/
}

```

### winUiTrackerObject.onMouseEnter

```aardio aardio
winUiTrackerObject.onMouseEnter = function(wParam,lParam){
    /*鼠标移入*/
}

```

### winUiTrackerObject.onMouseHWheel

```aardio aardio
winUiTrackerObject.onMouseHWheel = function(flags,delta,lParam){
    delta = -delta/(120/3);
    /*水平滚动鼠标滚轮,flags 参数�?_MK_CONTROL 等常量表示按�?/
}

```

### winUiTrackerObject.onMouseHover

```aardio aardio
winUiTrackerObject.onMouseHover = function(wParam,lParam){
    /*鼠标悬停*/
}

```

### winUiTrackerObject.onMouseLeave

```aardio aardio
winUiTrackerObject.onMouseLeave = function(wParam,lParam){
    /*鼠标移出*/
}

```

### winUiTrackerObject.onMouseMove

```aardio aardio
winUiTrackerObject.onMouseMove = function(wParam,lParam){
    if( wParam & 0x1/*_MK_LBUTTON*/ ){
        var x,y = win.getMessagePos(lParam);
        /*鼠标移动*/
    }
}

```

### winUiTrackerObject.onMouseUp

```aardio aardio
winUiTrackerObject.onMouseUp = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标左键弹起*/
}

```

### winUiTrackerObject.onMouseWheel

```aardio aardio
winUiTrackerObject.onMouseWheel = function(flags,delta,lParam){
    delta = delta/(120/3);
    /*滚动鼠标滚轮,flags 参数�?_MK_CONTROL 等常量表示按�?/
}

```

### winUiTrackerObject.onRightMouseDown

```aardio aardio
winUiTrackerObject.onRightMouseDown = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标右键按下*/
}

```

### winUiTrackerObject.onRightMouseUp

```aardio aardio
winUiTrackerObject.onRightMouseUp = function(wParam,lParam){
    var x,y = win.getMessagePos(lParam);
    /*鼠标右键弹起*/
}

```

### winUiTrackerObject.onSelectChange

```aardio aardio
winUiTrackerObject.onSelectChange = function(prev){
    /*单选模式下已选中当前控件,prev 为同一分组之前选中的控�?同一分组之前没有选中控件�?prev �?null*/
}

```

### winUiTrackerObject.onStateChange

```aardio aardio
winUiTrackerObject.onStateChange = function(){
    /*状态已改变*/
}

```

### winUiTrackerObject.onSysKeyDown

```aardio aardio
winUiTrackerObject.onSysKeyDown = function(keyCode,lParam,repeat){
    if(keyCode!=0x12/*_VK_ALT*/){
        /*按下键盘ALT组合�?/
    }
}

```

### winUiTrackerObject.onSysKeyUp

```aardio aardio
winUiTrackerObject.onSysKeyUp = function(keyCode,lParam){
    /*放开键盘�?/
}

```

### winUiTrackerObject.radioClick()

单选模式下选中控件

### winUiTrackerObject.radioValue()

单选模式下选中控件的文�?
### winUiTrackerObject.state.active

鼠标或键盘键按下状�?
### winUiTrackerObject.state.checked

是否选中状�?
### winUiTrackerObject.state.disabled

已禁�?
### winUiTrackerObject.state.dragging

是否按下鼠标且正在拖�?
### winUiTrackerObject.state.focus

是否已得到焦�?
### winUiTrackerObject.state.hover

鼠标是否在控件上�?
悬停超过预设时间后触发onMouseHover事件

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/win/ui/tracker.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/win/ui/tracker.md')

