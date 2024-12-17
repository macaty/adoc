[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: FFmpeg 鍏ラ棬

```aardio aardio
//FFmpeg 鍏ラ棬
import win.ui;
/*DSG{{*/
var winform = win.form(text="璋冪敤 FFmpeg";right=759;bottom=469)
winform.add(
edit={cls="edit";left=10;top=6;right=744;bottom=450;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

import process.ffmpeg;

var ffmpeg = process.ffmpeg(,"-version");
winform.edit.text = ffmpeg.readAll();

//璋冪敤 ffmpeg.exe锛孎Fmpeg鍙傛暟鐢ㄦ硶: https://quickref.me/zh-CN/docs/ffmpeg.html
var ffmpeg = process.ffmpeg("/",//鎸囧畾瑕佸鐞嗙殑鏂囦欢鎵�鍦ㄧ洰褰?    `-i "abc.m4a" -y -acodec libmp3lame -aq 0 "xyz.mp3"`);

//璇诲彇杩涚▼鎵�鏈夎緭鍑猴紝涓嶉樆濉炵晫闈紝浣嗙瓑寰呰繘绋嬬粨鏉燂紙闃诲浠ｇ爜鍚戝悗鎵ц锛?winform.edit.text = ffmpeg.readAll();

/*
涓嬮潰杩欐牱鍒嗗紑鍐欏弬鏁颁篃鍙互锛?鍖呭惈绌烘牸鎴栧瓨鍦ㄩ渶瑕佽浆涔夊瓧绗︾殑鍙傛暟浼氳嚜鍔ㄥ湪棣栧熬鍔犲弻寮曞彿骞朵綔杞箟澶勭悊銆?*/
var ffmpeg = process.ffmpeg("/",
    "-i","abc.m4a","-y","-acodec","libmp3lame","-aq", "0","xyz.mp3");

//鎸囧畾鐢ㄦ枃鏈寮傛鏄剧ず杩涚▼杈撳嚭锛堜笉闃诲浠ｇ爜鍚戝悗鎵ц锛?ffmpeg.logResponse(winform.edit);

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/FFmpeg/FFmpeg.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/FFmpeg/FFmpeg.md')

