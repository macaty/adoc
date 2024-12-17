[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 窗口程序 - 自适应缩放事件

```aardio aardio
//窗口程序 - 自适应缩放事件
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio form";right=759;bottom=469)
winform.add(
edit={cls="edit";left=13;top=16;right=740;bottom=443;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

/*
所�?win.form 创建的窗体和控件在调整窗口大小时都会触发 adjust 事件�?这个事件重复赋值时�?wndproc 一样是追加事件而非覆盖之前定义的事件�?将控件的 adjust 事件赋值为 null 则清空该事件�?
cx 为窗口宽度，cx 为窗口高度，wParam �?_WM_SIZE 消息参数（这个参数一般用不上）�?*/
winform.edit.adjust = function( cx,cy,wParam ) {
      winform.edit.print("winform.edit.adjust 被调用：",cx,cy,wParam);
};

/*
所�?win.form 创建的窗体和控件在调整窗口大小时都会触发 preadjust 事件�?�?preadjust 重复赋值时是覆盖之前定义的 preadjust 事件，而非追加该事件�?
win.form 窗体对象会在触发窗体与所有控件的 preadjust 事件以后调用 redraw() 函数重绘�?然后再调用窗体与所有控件的 adjust 事件�?
一般需要用�?preadjust 事件的情况很少，
并且因为 preadjust 总是会覆盖之前定义的事件，所以一般建议大家使�?adjust 而不�?preadjust�?*/
winform.edit.preadjust = function( cx,cy,wParam ) {
     winform.edit.print("winform.edit.preadjust 被调用：",cx,cy,wParam);
};

/*
这个事件�?adjust 的作用一样，�?_adjust 是一个只读属性�?_adjust 只能定义一次，定义后就不能被修改，也不会被移除�?
这个事件是被标准库保留的事件，也不会显示在智能提示列表中，请不要滥用�?*/
winform.edit._adjust = function( cx,cy,wParam ) {
      winform.edit.print("winform.edit._adjust 被调用：",cx,cy,wParam);
};

/*
这个事件�?preadjust 的作用一样，�?_preadjust 是一个只读属性�?_preadjust 只能定义一次，定义后就不能被修改，也不会被移除�?
这个事件是被标准库保留的事件，也不会显示在智能提示列表中，请不要滥用�?*/
winform.edit._preadjust = function( cx,cy,wParam ) {
      winform.edit.print("winform.edit._preadjust 被调用：",cx,cy,wParam);
};

/*
我们可以主动调用 adjust 事件，即使没有定�?adjust 或者清空了 adjust 事件�?省略参数时将会自动补上合适的 cx,cy,wParam 参数（win.form 对象默认取窗户区大小，其他控件默认取窗口大小）�?当主动调�?adjust() 函数时，会依次调用已定义�?preadjust,_preadjust,_adjust,adjust 事件�?*/
winform.edit.adjust();

//调用 resize 函数会发�?_WM_SIZE 消息，并调用 adjust() 函数，可选在参数中重新指定窗口大小�?winform.edit.resize();

/*
一般不建议仅仅为了响应窗口缩放而添加一�?wndproc 去处�?_WM_SIZE 消息�?wndproc 实际上会响应所有窗口消息（虽然我们在回调内可以去写判断语句）�?虽然一个窗口消息回调的消耗可能微不足道，但仍然是不必要的消耗�?
要注意只有在窗口实际变更大小后才会触�?_WM_SIZE （或者主动给窗口发这个消息）�?但是窗体变更大小后，总是会调用窗体自身与所有控件的 preadjust,adjust 等事件（无论他们的实际大小有没有变更）�?
控件�?setPos 函数也会主动调用 adjust() 函数�?但要了解控件自身收到 _WM_SIZE 默认并不会调�?adjust() 函数�?
例如我们执行 win.setPos(winform.edit.hwnd,0,0,200,300) 就只会触�?_WM_SIZE 消息�?但使�?winform.edit.setPos(0,0,200,300) 就可以触�?_WM_SIZE 消息，并调用 adjust() 函数�?*/
winform.edit.wndproc = function(hwnd,message,wParam,lParam){

    if(message==5/*_WM_SIZE*/){
        winform.edit.print("winform.edit.text 收到 _WM_SIZE 消息",::LOWORD(lParam),::HIWORD(lParam),wParam );
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Basics/adjust.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Basics/adjust.md')

