[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 浣跨敤WMI鐩戣杩涚▼鎵撳紑鍏抽棴浜嬩欢

```aardio aardio
//WMI 鐩戣杩涚▼
import win.ui;
/*DSG{{*/
var winform = win.form(text="浣跨敤WMI鐩戣杩涚▼鎵撳紑鍏抽棴浜嬩欢";right=759;bottom=469)
winform.add(
edit={cls="edit";left=16;top=16;right=744;bottom=448;edge=1;multiline=1;z=1}
)
/*}}*/

import com.wmi;
var wmi = com.wmi();

com.wmi.queryNotificationAsync({
    OnObjectReady = function(objObject, objAsyncContext) {
        var target = objObject.TargetInstance ();
        winform.edit.print("鍒涘缓杩涚▼. ",target.Name(),"杩涚▼ID:" + target.ProcessId)
        winform.edit.print(target.CommandLine)
    };
    OnCompleted = function(objObject, objAsyncContext) {
        winform.edit.print("鎿嶄綔宸插畬鎴?)
    };
    //WITHIN 鏉′欢鎸囧畾杞闂撮殧锛堜互绉掍负鍗曚綅锛夛紝渚嬪 WITHIN 5 鎸囧畾 5 绉掕疆璇竴娆°�?}, "SELECT * FROM __InstanceCreationEvent WITHIN 3 WHERE TargetInstance ISA 'Win32_Process'")

com.wmi.queryNotificationAsync({
    OnObjectReady = function(objObject, objAsyncContext) {
        winform.edit.print("鍏抽棴杩涚▼. ",objObject.TargetInstance ().Name())
    };
    OnCompleted = function(objObject, objAsyncContext) {
        winform.edit.print("鎿嶄綔宸插畬鎴?)
    }
} , "SELECT * FROM __InstanceDeletionEvent WITHIN 3 WHERE TargetInstance ISA 'Win32_Process'")

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/WMI/SWbemSink.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/WMI/SWbemSink.md')

