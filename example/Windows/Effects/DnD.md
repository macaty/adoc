[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 绐楀彛绋嬪簭 - 鏂囦欢鎷栨斁

```aardio aardio
//绐楀彛绋嬪簭 - 鏂囦欢鎷栨斁
import win.ui;
/*DSG{{*/
var winform = win.form(text="绐楀彛绋嬪簭 - 鏂囦欢鎷栨斁";right=759;bottom=469)
winform.add(
edit={cls="edit";left=69;top=34;right=693;bottom=377;autohscroll=false;edge=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

/*
鎷栨斁浼氳Е鍙?onDropFiles 浜嬩欢銆?瀹氫箟姝や簨浠朵細鑷姩鎵ц ::Shell32.DragAcceptFiles(winform.hwnd,true) 浠ュ惎鐢ㄦ嫋鏀炬敮鎸併�?
瑕佺壒鍒敞鎰忔湁绠＄悊鏉冮檺鐨勭獥鍙ｄ笉鑳芥帴鍙楁嫋鏀撅紝鏂扮郴缁熷凡缁忓畬鍏ㄧ姝簡杩欑鎿嶄綔銆?*/
winform.onDropFiles = function(files){
    winform.edit.print(files)
}

winform.text = "璇锋嫋鏀句竴涓垨澶氫釜鏂囦欢鍒扮獥鍙ｄ笂"

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Effects/DnD.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Effects/DnD.md')

