[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 简单串口助�?
```aardio aardio
import win.dlg.message;
import win.ui;
/*DSG{{*/
var winform = win.form(text="简单串口助�?;right=759;bottom=469)
winform.add(
btnOpen={cls="button";text="打开端口";left=85;top=411;right=183;bottom=445;db=1;dl=1;z=6};
btnTx={cls="button";text="发�?;left=582;top=411;right=680;bottom=445;db=1;dr=1;z=5};
combobox={cls="combobox";left=30;top=13;right=169;bottom=39;dl=1;dt=1;edge=1;items={};mode="dropdown";z=1};
editRx={cls="edit";left=29;top=62;right=727;bottom=396;db=1;dl=1;dr=1;dt=1;edge=1;multiline=1;z=2};
editTx={cls="edit";left=240;top=414;right=569;bottom=446;db=1;dl=1;dr=1;edge=1;z=4};
lbComPort={cls="static";text="没有找到任何串口，建议安装虚拟串口驱动： Virtual Serial Port Driver";left=199;top=16;right=607;bottom=40;dl=1;dr=1;dt=1;transparent=1;z=3};
openDeviceManager={cls="plus";text="打开设备管理�?;left=612;top=14;right=732;bottom=38;align="left";color=8388608;font=LOGFONT(h=-13);notify=1;textPadding={left=5};z=7}
)
/*}}*/

//串口列表
import sys.comPort;
var comPorts = sys.comPort.list();
winform.combobox.items = comPorts;
winform.combobox.selIndex = sys.comPort.find("CP210x")[["index"]] or 1;

//获取串口信息
winform.combobox.oncommand = function(id,event){
    var item = comPorts[winform.combobox.selIndex]
    if(item){
        winform.lbComPort.text = item.friendlyName;
    }
}
winform.combobox.oncommand();

//串口发�?import sio;
var sioPort;
winform.btnTx.oncommand = function(id,event){
    if(!sioPort){
        winform.btnOpen.oncommand();
    }

    if( !sioPort.write( winform.editTx.text ) ){
        return winform.msgErr("发送失�?);
    }
}

//打开串口
winform.btnOpen.oncommand = function(id,event){
    if(sioPort){
        sioPort.close();
    }

    var err;
    sioPort,err = sio.port(winform.combobox.selText);
    if(!sioPort){
        return winform.msgErr(err);
    }

    //sioPort.ioctl(115200,8,1);
    //串口接收到数据触发回�?    sioPort.termCntIrq(1,function(port){
        winform.editRx.appendText(sioPort.read());
    } )

    winform.msgOk("已打开端口",1000)
}

winform.onDestroy = function(){
    if(sioPort){
        sioPort.close();
    }
}

import sys.device;
winform.openDeviceManager.oncommand = function(id,event){
    sys.device.manager();
}

winform.openDeviceManager.skin({
    color={
        active=0xFF00FF00;
        default=0xFF000080;
        disabled=0xFF6D6D6D;
        hover=0xFFFF0000
    }
})

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/File/SerialPort/sio.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/File/SerialPort/sio.md')

