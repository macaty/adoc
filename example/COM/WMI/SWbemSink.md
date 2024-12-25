[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用WMI监视进程打开关闭事件

```aardio aardio
//WMI 监视进程
import win.ui;
/*DSG{{*/
var winform = win.form(text="使用WMI监视进程打开关闭事件";right=759;bottom=469)
winform.add(
edit={cls="edit";left=16;top=16;right=744;bottom=448;edge=1;multiline=1;z=1}
)
/*}}*/

import com.wmi;
var wmi = com.wmi();

com.wmi.queryNotificationAsync({
    OnObjectReady = function(objObject, objAsyncContext) {
        var target = objObject.TargetInstance ();
        winform.edit.print("创建进程. ",target.Name(),"进程ID:" + target.ProcessId)
        winform.edit.print(target.CommandLine)
    };
    OnCompleted = function(objObject, objAsyncContext) {
        winform.edit.print("操作已完�?)
    };
    //WITHIN 条件指定轮询间隔（以秒为单位），例如 WITHIN 5 指定 5 秒轮询一次�?}, "SELECT * FROM __InstanceCreationEvent WITHIN 3 WHERE TargetInstance ISA 'Win32_Process'")

com.wmi.queryNotificationAsync({
    OnObjectReady = function(objObject, objAsyncContext) {
        winform.edit.print("关闭进程. ",objObject.TargetInstance ().Name())
    };
    OnCompleted = function(objObject, objAsyncContext) {
        winform.edit.print("操作已完�?)
    }
} , "SELECT * FROM __InstanceDeletionEvent WITHIN 3 WHERE TargetInstance ISA 'Win32_Process'")

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/COM/WMI/SWbemSink.md)

