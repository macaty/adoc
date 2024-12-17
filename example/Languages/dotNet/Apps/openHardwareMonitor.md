[aardio 文档](../../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 利用开源库OpenHardwareMonitor获取CPU或显卡温�?
```aardio aardio
//RUNAS//aardio 调用 .NET 开源组件检测硬件温�?import win.ui;
/*DSG{{*/
var mainForm = win.form(text="aardio 利用开源库OpenHardwareMonitor获取CPU或显卡温�?;right=791;bottom=699)
mainForm.add(
edit={cls="edit";left=8;top=4;right=787;bottom=696;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

/*
请右键点�?sys.openHardwareMonitor
在弹出菜单内点「转到定�?/ 文件」查看库源码�?
这是一个调�?.NET 开源组件（OpenHardwareMonitorLib.dll）的演示�?aardio 可以内存加载 .NET 生成�?DLL 程序集，并生成独�?EXE 文件�?*/
import sys.openHardwareMonitor;
var computer = sys.openHardwareMonitor.computer();

computer.enumHardware(function(hardwareItem,path,index){
    hardwareItem.Update()
    mainForm.edit.print( path + hardwareItem.Name,hardwareItem.HardwareTypeString );

    for i,sensor in hardwareItem.eachSensors(){
        mainForm.edit.print(path+'\t',sensor.Name,sensor.ValueString,sensor.MaxString,sensor.SensorTypeString )
    }

    return path + '\t';
},"")

mainForm.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/openHardwareMonitor.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/dotNet/Apps/openHardwareMonitor.md')

