[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鐢垫簮绠＄悊鍏冲睆

```aardio aardio
//鐢垫簮绠＄悊鍏冲睆
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="鑷姩鍏冲睆";left=-20;top=50;right=319;bottom=99;bgcolor=16777215;border="none";max=false)
winform.add(
btnClose={cls="close";text="脳";left=297;top=11;right=325;bottom=39;bgcolor=13405076;dr=1;dt=1;font=LOGFONT(h=-21);z=3};
btnCloseLcd={cls="plus";text="鍏冲睆";left=191;top=14;right=240;bottom=33;color=8388608;notify=1;textPadding={left=5};z=5};
chkLock={cls="plus";text="閿佸睆";left=242;top=14;right=296;bottom=33;align="left";iconStyle={align="left";font=LOGFONT(name='FontAwesome')};iconText='\uF0C8 ';notify=1;textPadding={left=15};z=4};
datetimepick={cls="datetimepick";left=111;top=14;right=186;bottom=38;edge=1;transparent=1;updown=1;z=1};
lbTitle={cls="static";text="绌洪棽鏃堕棿瓒呰繃锛?;left=0;top=18;right=103;bottom=40;align="right";transparent=1;z=2}
)
/*}}*/

import win.ui.tooltip
var balloonTipCtrl = win.ui.tooltip.tracking(winform,false)

import sys.power;
winform.datetimepick.onDateTimeChanged = function(dateTime){

    if(tonumber(dateTime)<5){
        var x,y,cx,cy = winform.datetimepick.getPos(true);
        balloonTipCtrl.setText("灏忎簬 5 绉掞紝宸茬鐢ㄨ嚜鍔ㄥ叧灞忋�?).trackPopup(true,x+20,y+cy );

        sys.power.setMonitorTimeout(0);
    }
    else {
        balloonTipCtrl.trackPopup(false);
        sys.power.setMonitorTimeout(tonumber(dateTime));
    }
}

var timeout = sys.power.getMonitorTimeout() : 0;
winform.datetimepick.time = time.iso8601(timeout);
if(timeout<5) winform.datetimepick.onDateTimeChanged(timeout);
winform.datetimepick.setFormat("' 'HH':'mm':'ss");

import fsys.config;
var config = fsys.config(io.appData("aardio/std/closeLcd"))

//娉ㄥ唽鐢垫簮璁剧疆浜嬩欢閫氱煡绐椾綋
import sys.power.notification;
var sn = sys.power.notification(winform,"6FE69556-704A-47A0-8F24-C28D936FDA47");

import sys;
sn.onPowerSettingChange = function(guid,data){
    if(data == 0 && config.setting.lock){
        sys.lock(); //鍏冲睆鏃惰嚜鍔ㄩ攣灞?    }
}

winform.onMouseDown = function(){
    balloonTipCtrl.trackPopup(false);
    winform.hitCaption();
}

winform.chkLock.oncommand = function(id,event){
    config.setting.lock = winform.chkLock.checked;
    config.setting.save();
}

//涓诲姩鍏冲睆
winform.btnCloseLcd.oncommand = function(id,event){
    //寤舵椂寮傛鎵ц锛岄伩鍏嶆樉绀哄櫒鍒氬叧鎺夊張琚敜閱?    winform.setTimeout(
        function(){
            //鐢?User32.SendMessage浼氬崱锛屾敼鐢ㄥ紓姝ョ殑::User32.SendNotifyMessage
            ::User32.SendNotifyMessage( 0xFFFF/*_HWND_BROADCAST*/ ,0x112/*_WM_SYSCOMMAND*/, 0xF170/*_SC_MONITORPOWER*/ ,2);
        },200 //缁欎竴鐐瑰欢鏃讹紝涓囦竴榧犳爣杩樺湪鏅冨憿?
    )
}

winform.chkLock.checked = config.setting.lock;

winform.btnCloseLcd.skin({
    color={
        active=0xFF00FF00;
        default=0xFF000080;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
})

winform.chkLock.skin(
    color = {
        hover = 0xFFFF0000;
        active = 0xFF00FF00;
    }
    checked = {
        iconText = '\uF14a';
    }
)

//鐐瑰嚮 close 鎺т欢鍏抽棴绐楀彛銆?winform.btnClose.oncommand = function(id,event){
    winform.close();
}
winform.btnClose.show(true);

import win.ui.shadow;
win.ui.shadow(winform);

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/System/Hardware/monitorPower.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/System/Hardware/monitorPower.md')

