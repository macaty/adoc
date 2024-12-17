[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 超级热键演示

```aardio aardio
//超级热键
//教程: https://www.aardio.com/zh-cn/doc/?q=library-guide/std/key/hotkey.html
import win.ui;
/*DSG{{*/
var winform = win.form(text="超级热键演示";right=796;bottom=434;bgcolor=16777215)
winform.add(
edit={cls="edit";left=8;top=8;right=784;bottom=360;edge=1;multiline=1;z=1};
editLog={cls="edit";left=9;top=375;right=784;bottom=427;bgcolor=16777215;multiline=1;z=2}
)
/*}}*/

import key.hotkey;
var superHotkey = key.hotkey() //只能在界面线程创建超级热�?
//批量加载热键配置�?superHotkey.loadTable({
    (function(){
        //这里的代码可以直接执�?    })();

    /* 大写金额(可输入数学表达式)、日期、时�? */
    ["Ctrl+$"] = function(hFocus){
        win.dlg.chineseNumber().show();
    };
});
import win.dlg.chineseNumber;

superHotkey.reg(
    "CTRL","K",
    function(hwnd,...){
        ..winex.say("你按了CTRL+K!")
    }
)

superHotkey.reg(
    "CTRL","K","K",
    function(hwnd,...){
        ..winex.say("你按了CTRL+K,K!")
    }
)

//添加新的热键方案
superHotkey.reg(
    "~","H","I",
    function(hwnd,...){
        ..winex.say("hello world!")
    }
)

//添加新的热键方案
import fsys.lnk;
import process;
superHotkey.reg(
    "SHIFT","Q","Q",
    function(hwnd,...){
        var path  = fsys.lnk.search( {"qq.exe";"QQScLauncher.exe";"QQProtect.exe"} ) ;
        process.execute(path)
    }
)

superHotkey.regStr(
    "@SHIFT",
    function(hwnd,...){
        ..winex.say("单按 SHIFT")
    }
)

superHotkey.regStr(
    "~aa",
    function(hwnd,...){
        ..winex.say("http://www.aardio.com",hwnd)
    }
)

//允许在下面的事件中拦截所有按键，返回 true 阻止按键消息
superHotkey.onKeyDown = function(vk){

}

superHotkey.setEndKeys("SPACE")

//可选指定下面的触发器函�? 当用户按下部分热键、并有一个或多个可能的候选键时触�?import win.util.tray;
superHotkey.onWaiting = function(hwnd,enteredKeys,waitingKeys){

    if(!enteredKeys){
        winform.editLog.text = "准备就绪......";
        return;
    }

    winform.editLog.text =   '已按�?'
        + ..string.join(enteredKeys,"+")
        + ' 等待候选键:'
        + ..string.join(waitingKeys,",")
        ,"超级热键模式已启�?
}

winform.edit.text = /*
热键  Ctrl+$  用法：按�?Ctrl 不放，再�?
热键  Ctrl+K  用法：按�?Ctrl 不放，再按K, 然后都放开
热键  Ctrl+K,K    用法：按下Ctrl不放，再�?次K
热键  @Shift  用法：按�?Shift 再放开，中间不按其他键，通常不会阻止 Shift 切换输入法状态的默认热键�?热键  ~hi 用法：依次按键，每个键都放开
热键  Shift+Q,Q   用法：按下Shift不放，再�?下Q
热键  ~AA 用法：依次按键，每个键都放开

点这�?连续按上面各行的键�?注意这是超级热键，不是热字符串，以键为输入单位而不是字符�?例如 ~hi 只按3次键，第一个键不要按Shift + `

超级热键是操作系统级别的热键，系统全局可用�?
超级热键的更多用法请参考开源软�?ImTip (http://imtip.aardio.com)

超级热键使用指南: https://www.aardio.com/zh-cn/doc/library-guide/std/key/hotkey.html
*/

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/key.hotkey.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Hotkey/key.hotkey.md')

