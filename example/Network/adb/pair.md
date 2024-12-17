[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 安卓手机扫码配对，无线调�?
```aardio aardio
//扫码配对
import win.ui;
/*DSG{{*/
var winform = win.form(text="安卓手机扫码配对，无线调�?;right=564;bottom=593;bgcolor=16777215)
winform.add(
button={cls="button";text="连接�?...";left=299;top=542;right=530;bottom=575;db=1;disabled=1;dr=1;z=5};
edit={cls="edit";left=19;top=411;right=544;bottom=535;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
editPort={cls="edit";left=158;top=546;right=274;bottom=573;db=1;dr=1;edge=1;num=1;z=3};
plus={cls="plus";left=19;top=22;right=544;bottom=400;db=1;dl=1;dr=1;dt=1;repeat="scale";z=1};
static={cls="static";text="请输入连接端口：";left=9;top=550;right=139;bottom=574;align="right";db=1;dr=1;transparent=1;z=4}
)
/*}}*/

/*
adb 文档�?http://developer.android.com/tools/help/adb.html
process.adb.startServer 启动 adb 服务端，这个函数实际上会自动调用一次，
adb 需要一个常驻服务端（启动一�?adb.exe 进程），也只能有一个服务进程，多个会工作不正常�?这个扩展库会自动查找之前启动�?adb 服务端，如果找到就直接重用�?进程退出时不会退出常驻服务端（一般无此必要）

每次发�?adb 指令时也会启动一�?adb 客户端，这也是一�?adb.exe 进程�?所�?adb 客户端在执行完成后，或当前进程退出后将会自动关闭（由 process.job.limitKill 实现）�?*/
import process.adb;
winform.button.oncommand = function(id,event){

    var str = process.adb.connect(owner.adbInfo.addr + ":" + winform.editPort.text,true);
    if(str){
        winform.msgbox(str)

        //执行 shell 命令
        var adb = process.adb.shell("ls");
        var out = adb.readAll(); //读取进程输出，adb 是一�?process.popen 对象，请参考该库函数文档�?        winform.edit.print(out);

        //上传文件
        //process.adb.push( "/abc.txt","/mnt/sdcard/abc.text" );
    }
    else {
        winform.msgboxErr("连接失败，请输入正确端口")
    }
}

winform.onAdbPair = function(info){
    if(info){
        winform.edit.print("配对成功�?,info);
        winform.button.text = "连接到：" + info.addr;
        winform.button.adbInfo = info;
        winform.button.disabled = false;
    }

    return true;//返回 false 停止此二维码的自动配�?}

import process.adb.qrCode;
var qrBmp = process.adb.qrCode(winform );
winform.plus.setBackground(qrBmp.copyBitmap(winform.plus.width));

winform.edit.text = /*
手机与电脑连接到同一无线局域网�?然后打开安卓手机 > 设置 > 开发者选项 > 无线调试 > 扫二维码配对
*/

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/adb/pair.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/adb/pair.md')

