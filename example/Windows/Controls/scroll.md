[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 滚动条、滑尺控件、微调按�?
```aardio aardio
//滚动�?滑尺控件
import win.ui;
/*DSG{{*/
var winform = win.form(text="滚动条、滑尺控件、微调按�?;right=438;bottom=203;max=false;)
winform.add(
editScrollbar={cls="edit";text="1";left=46;top=89;right=119;bottom=114;db=1;dl=1;edge=1;multiline=1;readonly=1;z=4};
editSpin={cls="edit";text="1";left=43;top=137;right=98;bottom=163;align="right";db=1;dl=1;edge=1;multiline=1;z=5};
editTrackbar={cls="edit";text="0.1";left=46;top=41;right=119;bottom=66;align="center";db=1;dl=1;edge=1;readonly=1;z=3};
scrollbar={cls="scrollbar";left=141;top=88;right=375;bottom=118;db=1;dl=1;horz=1;tabstop=1;z=2};
spin={cls="spin";left=77;top=139;right=97;bottom=160;db=1;dl=1;z=6};
trackbar={cls="trackbar";left=135;top=39;right=375;bottom=69;db=1;dl=1;max=0;min=0;z=1}
)
/*}}*/

//指定滑尺(跟踪�?范围
winform.trackbar.setRange(1,50)

winform.trackbar.oncommand = function(id,event,pos){

    /**
    跟踪条的事件ID与滚动条类似,
    例如_TB_ENDTRACK 其实就是滚动条中�?_SB_ENDSCROLL(event的值都�?)

    在调整跟踪条结束以后，都会触发_TB_ENDTRACK �?    例如用户拖动滑块以后放开，或按方向箭，翻页箭，鼠标点击等等，

    而拖动滑块时会触�?0x5/*_TB_THUMBTRACK*/
    拖动结束会触�?0x4/*_TB_THUMBPOSITION*/

    仅_TB_THUMBTRACK,_TB_THUMBPOSITION事件中pos的值等于winform.trackbar.pos�?    其他事件中为0,

    **/

    if( event == 0x8/*_TB_ENDTRACK*/ ){
        //winform.editTrackbar.text = winform.trackbar.pos;
    }

    //winform.trackbar.pos的值总是最新的，简单一点可以这样写
    var pos = winform.trackbar.pos;
    winform.editTrackbar.text = pos / 10; //显示为小�?    winform.trackbar.tooltip = pos / 10; //显示为小�?如果没这个需�?这句可删�?}

//自绘- 强行移除滑尺控件获得焦点后显示的虚线�?winform.trackbar.onnotify = function(id,code,ptr){
    if( code == 0xFFFFFFF4/*_NM_CUSTOMDRAW*/ ){
        var lvcd = winform.trackbar.getNotifyCustomDraw(code,ptr);
        if( lvcd.dwDrawStage == 1/*_CDDS_PREPAINT*/ ){
            lvcd.uItemState = lvcd.uItemState &  ~0x10/*_CDIS_FOCUS*/;
            lvcd.update();
        }
    }
}

winform.scrollbar.setRange(1,100)
winform.scrollbar.oncommand = function(id,event,pos){
    /*
    例如用户拖动滑块以后放开，或按方向箭，翻页箭，鼠标点击等等，
    在调整跟踪条结束以后，都会触发_TB_ENDTRACK ，注意这时候winform.scrollbar.pos值已经更新了�?    而回调参数pos这时候是无效的�?    */
    if( event == 0x8/*_SB_ENDSCROLL*/ ){
        winform.editScrollbar.text = winform.scrollbar.pos;
    }
    else {

        if( event == 0x0/*_SB_LINEUP*/ ){
            winform.scrollbar.pos -= 1
        }
        elseif( event == 0x1/*_SB_LINEDOWN*/ ){
            winform.scrollbar.pos += 1
        }
        elseif( event ==0x5/*_SB_THUMBTRACK*/){
            winform.scrollbar.pos = pos; //滚动条要存储新刻�?        }

        winform.editScrollbar.text = winform.scrollbar.pos;
    }
}

/*
指定 spin 控件同步数值的文本�?spin 控件可以放在 buddy(edit控件)内部靠左侧、靠右侧（推荐做法）�?
也可以放在buddy(edit控件)外部靠左侧、靠右侧，调整窗口大小时 spin 控件会自动吸附在buddy(edit控件)对应侧�?如果buddy 在外部，建议�?spin 控件构造参数中添加 align="right" �?align="left"�?*/
winform.spin.buddy = winform.editSpin;
winform.spin.setRange(1,100); //一定要设置数值的上下�?winform.spin.pos = 1;//设置数�?winform.spin.inc  = 10;//设置每次点击箭头的增减量（步长）

//处理spin事件
winform.spin.oncommand = function(id,event,pos){
    if( pos && event == 0x4/*_SB_THUMBPOSITION*/ ){
        winform.text = "spin" + winform.editSpin.text
    }
}

//处理spin事件通知,将要改变值之前触�?winform.spin.onnotify = function(id,code,ptr){
    if(code==0xFFFFFD2E/*_UDN_DELTAPOS*/){
        var nmUpDown = ..raw.convert(ptr, {
            struct hdr = ::NMHDR();
            int pos; //当前位置
            int delta; //位置的增减量,单击向上箭头此值为负数
        } );
    }
}

//spin绑定的文本框事件
winform.editSpin.oncommand = function(id,event){
    if( event = 0x200/*_EN_KILLFOCUS*/ ){
        winform.text = "spin" + winform.editSpin.text
    }
}

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/scroll.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/scroll.md')

