[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 涓枃鍒嗚瘝

```aardio aardio
//涓枃鍒嗚瘝
import win.ui;
/*DSG{{*/
var winform = win.form(text="mmseg test";right=759;bottom=469)
winform.add(
richedit={cls="richedit";left=38;top=33;right=723;bottom=423;bgcolor=16777215;edge=1;hscroll=1;multiline=1;vscroll=1;wrap=1;z=1}
)
/*}}*/

import mmseg
var str = /*
MMSEG锛圡aximum Matching Segmentation锛夋槸涓�绉嶉珮鏁堢殑涓枃鍒嗚瘝绠楁硶锛屽畠閲囩敤浜嗘渶闀垮尮閰嶅師鍒欙紝鑳藉鏈夋晥鍦板鐞嗘涔夐棶棰橈紝閫傜敤浜庡绉嶅簲鐢ㄥ満鏅紝濡傛悳绱㈠紩鎿庛�佷俊鎭绱㈢瓑
*/

//鍔犺瘝锛屼篃鍙互鐢?mmseg.loadWords 鍔犺浇璇嶅吀鏂囦欢
mmseg.addWord("搴旂敤鍦烘櫙")

for word,attr in mmseg.each(str){
    winform.richedit.appendText( word," " )
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/mmseg.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/mmseg.md')

