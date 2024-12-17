[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 歌词解析，WMPlayer.OCX 音频播放控制，显示播放进�?
```aardio aardio
//LRC 歌词解析
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
var winform = win.form(text="歌词解析，WMPlayer.OCX 音频播放控制，显示播放进�?;right=695;bottom=374;border="dialog frame";max=false;min=false)
winform.add(
btnPause={cls="plus";text="暂停";left=445;top=335;right=544;bottom=363;align="left";bgcolor=-5197169;disabled=1;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=14;top=2}};iconText='\uF04C';notify=1;textPadding={left=35};z=6};
btnPlay={cls="plus";text="播放";left=562;top=335;right=652;bottom=363;align="left";bgcolor=-5197169;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=14;top=2}};iconText='\uF04B';notify=1;textPadding={left=35};z=5};
edit={cls="richedit";left=15;top=68;right=414;bottom=327;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;readonly=1;vscroll=1;z=3};
lbBrowser={cls="static";left=427;top=67;right=682;bottom=326;db=1;dr=1;dt=1;notify=1;z=2};
lbWmplayer={cls="static";left=15;top=9;right=682;bottom=53;dl=1;dr=1;dt=1;notify=1;z=1};
plus={cls="plus";text='\uF027';left=10;top=339;right=35;bottom=362;color=1938422;db=1;dr=1;font=LOGFONT(h=-19;name='FontAwesome');repeat="scale";z=7};
progress={cls="plus";left=15;top=57;right=682;bottom=61;bgcolor=6447459;forecolor=9959653;notify=1;z=4};
volume={cls="plus";left=40;top=343;right=156;bottom=355;bgcolor=-2512093;border={radius=-1};color=23807;db=1;dr=1;foreRepeat="expand";foreRight=13;forecolor=-14911489;notify=1;paddingBottom=5;paddingTop=5;z=8}
)
/*}}*/

winform.edit.text  = /*
下面的歌词考虑到了各种不规范写�?但string.lrc都可以解析出�? [ti:给我一首歌的时间]
 [ar:周杰伦]
 [al:魔杰座]
  [offset:200]
 歌词时间补偿，在显示歌词的timer事件中加入计算，目的是方便后期实现用户自定义歌词补偿时间
 [00:02.00]周杰�?- 给我一首歌的时�? 支持00:02�?0:02.10�?0:02.100
 [00:04.00]词：周杰�?曲：周杰�? [00:06.00]
 [00:08.00]放飞心情
 [00:10.00]
 无关字符串~~~~无关字符串~~~~
 [00:18.020][01:31.057]雨淋湿了天空（缺少换行）[01:33.60][00:20.35]毁得很讲�?[00:22.30][01:35.63]你说你不�? [00:23.086][01:37.013]为何在这时牵�? [01:39.66][00:26]我晒干了沉默
 [00:28.47][01:41]悔得很冲�? [00:30.52][01:43]就算这是做错
 [01:45.31][00:32]也只是怕错�? [00:34.24]
 无关字符串~~~~无关字符串~~~~
 [00:34][01:48]在一起叫梦（缺少毫秒�? [01:50][00:37]分开了叫痛（缺少毫秒�? [00:39][01:52]是不是说（缺少毫秒）
 [01:53.41][00:40.22]没有做完的梦最�? [00:43.11][01:56.28]迷路的后�? [01:58.23][00:45.06]我能承受
 [00:46.31][01:59.54]这最后的出口
 [00:48.62][02:01.80]在爱过了才有
 [00:52.49]
 [03:31.81][00:53.19][01:09.44][03:15.55][02:06.47][02:22.64]能不能给我一首歌的时�? [02:10.47][00:57.25][03:19.61]紧紧的把那拥抱变成永�? [01:01.33][02:14.51][03:23.63]在我的怀里你不用害怕失�? [02:18.57][03:27.75][01:05.32]�?如果你想忘记我也能失�? [01:13.52][02:26.74][03:35.91]把故事听到最后才说再�? [02:30.76][01:17.52][03:40.67]你送我的眼�? [02:32.65][01:19.38][03:42.24]让它留在雨天
 [01:21.64][02:34.92][03:44.56]�?越过你划的线
 [02:37.21][01:23.97][03:46.37]我定了勇气的终点
 [01:29.01]
 [01:47.39]
 [02:43.11][03:57.82][03:49.71]你说我不该不�? [03:51.46][02:45.83][03:59.58]不该在这时候说了我爱你
 [02:52.41][04:01.64][03:53.45]要怎么证明我没有说谎力�? [02:59.45]请告诉我暂停算不算放�? [03:08.67][04:03.98]我只有一天的回忆
 [03:14.85]
 [03:49.01]
 [03:55.78]可是我只有一天的回忆
 [03:57.12]
 [04:06.81]~~End~~
*/

import string.lrc;
var lyric = string.lrc( winform.edit.text )
winform.edit.text = lyric.stringify();//重新格式化lrc歌词

import web.form;
var wb = web.form( winform.lbBrowser );
var html = `<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
<style>
li{ list-style-type:square; font-size:10.5pt;color:#000000 }
li.lrcCur {
    color:#00CCFF
}
</style></head>
<body><ul>`

for( line,ms in lyric.each() ){
    html = html + "<li>" + line + "</li>"
}

wb.html = html + `</ul>
<script type="text/javascript">
var lrcList=document.getElementsByTagName('li');
var lrcCur;
window.lrcNext = function(idx){
    if( lrcCur ) lrcCur.className = '';
    lrcCur = lrcList[idx];
    lrcCur.className = 'lrcCur';
    window.scrollTo(0,lrcCur.offsetTop-100);
}
</script>`;

//创建播放器控�?//https://learn.microsoft.com/en-us/windows/win32/wmp/object-model-reference-for-scripting
var wmp = winform.lbWmplayer.createEmbedEx( "WMPlayer.OCX" );

wmp.uiMode = "none";
//wmp.settings.autoStart = false;
wmp.url = "http://download.aardio.com/v10.files/demo/mp3/lrc.mp3";

wmp.MediaChange = function(item){
    winform.progress.setProgressRange(0,wmp.currentMedia.duration);
    winform.progress.hide = false;
}

wmp.PlayStateChange = function(state) {
    if(state==3){
        winform.btnPause.disabled = false;
        winform.btnPlay.checked = true;
    }
    elseif(state<=1){
        winform.btnPause.disabled = true;
        winform.btnPause.checked = false;
        winform.btnPlay.checked = false;
        wb.script.lrcNext(0);
    }
};

//创建定时器用于同步歌�?winform.setInterval(
    function(){
        var ms = wmp.controls.currentPosition * 1000;

        if(ms){
            var i,j,delay = lyric.find(ms)
            if(i) {
                try{ wb.script.lrcNext(i-1); }
                return delay;//修改定时器的延时为当前歌词显示时�?            }
        }
    },100
);

//显示进度
winform.setInterval(
    function(){
        if(winform.btnPlay.checked){
            winform.progress.progressPos = wmp.controls.currentPosition;
        }
    },200
);

winform.onClose = function(hwnd,message,wParam,lParam){
      wb.write("");
}

winform.btnPlay.oncommand = function(id,event){

    if(!winform.btnPlay.checked){
        if(wmp.playState>1){
            wmp.Controls.stop();
            winform.progress.progressPos = 0;
        }
        return;
    }

    wmp.Controls.play();
}

winform.btnPause.oncommand = function(id,event){
    if(wmp.playState==3){
        wmp.Controls.pause();
    }
    elseif(wmp.playState==2){
        wmp.Controls.play();
    }
}

winform.volume.setTrackbarRange(1,100);
winform.volume.progressPos = 100;
winform.volume.onPosChanged = function( pos,triggeredByUser ){
    if(triggeredByUser){
        wmp.settings.volume = winform.volume.progressPos;
    }
}

winform.volume.skin({
    background={
        default=0xFF23ABD9
    };
    foreground={
        default=0xFFFF771C;
        hover=0xFFFF6600
    };
    color={
        default=0xFFFF5C00;
        hover=0xFFFF6600
    }
})

winform.btnPause.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    };
    checked = {
        iconText = '\uF04B';
        text = "继续";
        background={
            default=0x668FB2B0;
            disabled=0xFFCCCCCC;
            hover=0xFF928BB3
        };
        color={
            default=0xFF000000;
            disabled=0xFF6D6D6D
        };
    }
})

winform.btnPlay.skin({
    background={
        default=0x668FB2B0;
        disabled=0xFFCCCCCC;
        hover=0xFF928BB3
    };
    color={
        default=0xFF000000;
        disabled=0xFF6D6D6D
    };
    checked = {
        iconText = '\uF04D';
        text = "停止";
        background={
            default=0x668FB2B0;
            disabled=0xFFCCCCCC;
            hover=0xFF928BB3
        };
        color={
            default=0xFF000000;
            disabled=0xFF6D6D6D
        };
    }
})

winform.show();
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/lrc.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/lrc.md')

