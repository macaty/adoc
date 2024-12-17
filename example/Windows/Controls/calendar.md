[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛绋嬪簭 - 鏃ュ巻鏃堕棿鎺т欢

```aardio aardio
//绐楀彛绋嬪簭 - 鏃ュ巻鏃堕棿鎺т欢
import win.ui;
/*DSG{{*/
var winform = win.form(text="鏃ュ巻鎺т欢婕旂ず";right=440;bottom=249;)
winform.add(
button={cls="button";text="鍚屾鎺т欢鏃堕棿";left=302;top=205;right=422;bottom=233;db=1;dr=1;z=2};
calendar={cls="calendar";left=20;top=8;right=426;bottom=195;db=1;dl=1;dr=1;dt=1;edge=1;transparent=1;z=1};
datetimepick={cls="datetimepick";left=46;top=209;right=287;bottom=229;db=1;dr=1;edge=1;z=3}
)
/*}}*/

//鍏充簬鏍煎紡鍖栧瓧绗︿覆 http://msdn.microsoft.com/en-us/library/windows/desktop/bb761726(v=vs.85).aspx#dtp_format_chars
winform.datetimepick.setFormat("'鏃堕棿'hh':'m':'s ddddMMMdd', 'yyy")

winform.button.oncommand = function(id,event){
     winform.calendar.time = winform.datetimepick.time
}
winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Controls/calendar.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Controls/calendar.md')

