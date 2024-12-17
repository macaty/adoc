[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绯荤粺浠诲姟鏍忔樉绀鸿繘搴? 璋冪敤ITaskbarList3鎺ュ彛 )

```aardio aardio
//绐楀彛绋嬪簭 - 鍦ㄧ郴缁熶换鍔℃爮鏄剧ず杩涘害
import win.ui;
/*DSG{{*/
var winform = win.form(text="绯荤粺浠诲姟鏍忔樉绀鸿繘搴? 璋冪敤ITaskbarList3鎺ュ彛 )";right=599;bottom=399)
winform.add(
button={cls="button";text="鏄剧ず浠诲姟鏍忚繘搴?;left=219;top=240;right=459;bottom=327;z=1}
)
/*}}*/

import com.interface.ITaskbarList3;
winform.wndproc = function(hwnd,message,wParam,lParam){
    select( message ) {
        case _WM_TASKBARBUTTONCREATED{
            winform.taskbar = com.interface.ITaskbarList3.Create()
        }
    }
}

winform.button.oncommand = function(id,event){
    if(!winform.taskbar) return; //XP涓嬭鍊间负绌烘墍鏈変細蹇界暐涓嬮潰鐨勪唬鐮?
    for(i=1;10;1){
        winform.taskbar.SetProgressValue(winform.hwnd,i,10)
        win.delay(1000)
    }
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/ITaskbarList3.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/ITaskbarList3.md')

