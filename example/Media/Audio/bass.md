[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: bass

```aardio aardio
import fonts.fontAwesome;
import win.ui;
/*DSG{{*/
mainForm = win.form(text="bass ";right=521;bottom=88;max=false)
mainForm.add(
btnPlay={cls="plus";text="播放";left=412;top=4;right=511;bottom=32;align="left";bgcolor=-5197169;font=LOGFONT(h=-16);iconStyle={align="left";font=LOGFONT(h=-16;name='FontAwesome');padding={left=14}};iconText='\uF04B';textPadding={left=35};z=5};
cmbDevices={cls="combobox";left=8;top=5;right=401;bottom=31;edge=1;items={};mode="dropdown";z=4};
fftPane={cls="plus";left=25;top=110;right=568;bottom=250;notify=1;z=2};
plusLrc={cls="plus";left=11;top=35;right=595;bottom=62;font=LOGFONT(h=-19);z=3};
progress={cls="plus";left=11;top=77;right=506;bottom=81;bgcolor=6447459;forecolor=9959653;notify=1;z=1}
)
/*}}*/

import bass.channel;

//获取音频设备
var devices = bass.getDeviceInfos();
mainForm.cmbDevices.items = table.map(devices,lambda(v,k) v.name )

//选择默认设备
mainForm.cmbDevices.selIndex  = table.find(devices,lambda(v) v.flags & 2/*_BASS_DEVICE_DEFAULT*/)

mainForm.btnPlay.oncommand = function(id,event){
    if(mainForm.audio && !mainForm.btnPlay.checked) return mainForm.audio.stop();
     bass.setDevice(mainForm.cmbDevices.selIndex)
    var audio,err = bass.channel.open("http://download.aardio.com/v10.files/demo/mp3/lrc.mp3")
    if( err ) return mainForm.msgboxErr(err);

    //切换输出设备
    audio.setDevice(mainForm.cmbDevices.selIndex)

    // 设置同步回调函数
    audio.syncCallback(function(data){
        mainForm.text = "正在播放:" + audio.getInfo().filename
    },0/*_BASS_SYNC_POS*/,0)

    // 析构回调
    audio.syncCallback(function(data){
        audio.free()
    },2/*_BASS_SYNC_END*/)

    // 获取音频时长
    mainForm.progress.setProgressRange(0,audio.duration());

    // 音频播放进度回调
    audio.posCallback(
        function(seconds){
            mainForm.fftPane.fftData = table.map( audio.getData(0x80000001/*_BASS_DATA_FFT512*/),math.abs );
            mainForm.fftPane.redrawTransparent();

            mainForm.progress.progressPos = seconds;
            mainForm.plusLrc.text = mainForm.lyric.findLrc(seconds*1000)
        },200
    )

    audio.play();
    mainForm.audio = audio;
}
mainForm.fftPane.orphanWindow(true);

var brush = gdip.solidBrush(0xFF8B0000);
var pen = gdip.pen( 0xFF540000, 1, 2/*_GdipUnitPixel*/ );
mainForm.fftPane.onDrawBackground = function(graphics,rc,bkColor,foreColor){
    // 画频谱函数参考武斌提供的豆瓣FM客户端源�?    var fftData = owner.fftData;
    if(!fftData) return;

    var fftNum = 66;
    var peacks = {};
    var fallOff = {};
    for(i=1;math.floor(fftNum/2)+1;1) {
        peacks[i] = 0;
    }

    var x,y,cx,cy = rc.xywh();
    var fftHeight = 120;
    var w = 8;

    var j = 1;
    for(i=1;fftNum;2) {
        if(!fftData[i]) return;
        fallOff[j] = 0;

        var di = math.floor((fftData[i]+fftData[i+1])/2*900);
        if(di > fftHeight) di = fftHeight;
        if(di >= peacks[j]) peacks[j] = di else peacks[j] = peacks[j] -3;
        if(di >= fallOff[j]) fallOff[j] = di else fallOff[j] = fallOff[j] - 5;

        if((fftHeight - peacks[j]) > fftHeight) peacks[j] = 0;
        if((fftHeight - fallOff[j]) > fftHeight) fallOff[j] = 0;
        if(peacks[j]<1) peacks[j] = 1;
        if(fallOff[j]<0) fallOff[j] = 0;

        graphics.fillRectangle(brush, j * (w + 1), fftHeight - fallOff[j], w, fallOff[j] );
        graphics.drawLine( pen, j * (w + 1), fftHeight - peacks[j], j * (w + 1) + w-1, fftHeight - peacks[j]);
        j++;
    }
}

var strLrc = /*
[ti:给我一首歌的时间]
[ar:周杰伦]
[al:魔杰座]
[00:02.00]周杰�?- 给我一首歌的时�?[00:04.00]词：周杰�?曲：周杰�?[00:06.00]
[00:08.00]放飞心情
[00:10.00]
[00:18.20]雨淋湿了天空
[00:20.35]毁得很讲�?[00:22.30]你说你不�?[00:23.86]为何在这时牵�?[00:26.54]我晒干了沉默
[00:28.47]悔得很冲�?[00:30.52]就算这是做错
[00:32.21]也只是怕错�?[00:34.24]
[00:34.94]在一起叫�?[00:37.02]分开了叫�?[00:39.01]是不是说
[00:40.22]没有做完的梦最�?[00:43.11]迷路的后�?[00:45.06]我能承受
[00:46.31]这最后的出口
[00:48.62]在爱过了才有
[00:52.49]
[00:53.19]能不能给我一首歌的时�?[00:57.25]紧紧的把那拥抱变成永�?[01:01.33]在我的怀里你不用害怕失�?[01:05.32]�?如果你想忘记我也能失�?[01:09.44]能不能给我一首歌的时�?[01:13.52]把故事听到最后才说再�?[01:17.52]你送我的眼�?[01:19.38]让它留在雨天
[01:21.64]�?越过你划的线
[01:23.97]我定了勇气的终点
[01:29.01]
[01:31.57]雨淋湿了天空
[01:33.60]毁得很讲�?[01:35.63]你说你不�?[01:37.13]为何在这时牵�?[01:39.66]我晒干了沉默
[01:41.71]悔得很冲�?[01:43.75]就算这是做错
[01:45.31]也只是怕错�?[01:47.39]
[01:48.09]在一起叫�?[01:50.13]分开了叫�?[01:52.09]是不是说
[01:53.41]没有做完的梦最�?[01:56.28]迷路的后�?[01:58.23]我能承受
[01:59.54]这最后的出口
[02:01.80]在爱过了才有
[02:05.77]
[02:06.47]能不能给我一首歌的时�?[02:10.47]紧紧的把那拥抱变成永�?[02:14.51]在我的怀里你不用害怕失�?[02:18.57]�?如果你想忘记我也能失�?[02:22.64]能不能给我一首歌的时�?[02:26.74]把故事听到最后才说再�?[02:30.76]你送我的眼�?[02:32.65]让它留在雨天
[02:34.92]�?越过你划的线
[02:37.21]我定了勇气的终点
[02:42.41]
[02:43.11]你说我不该不�?[02:45.83]不该在这时候说了我爱你
[02:52.41]要怎么证明我没有说谎力�?[02:59.45]请告诉我暂停算不算放�?[03:08.67]我只有一天的回忆
[03:14.85]
[03:15.55]能不能给我一首歌的时�?[03:19.61]紧紧的把那拥抱变成永�?[03:23.63]在我的怀里你不用害怕失�?[03:27.75]�?如果你想忘记我也能失�?[03:31.81]能不能给我一首歌的时�?[03:35.91]把故事听到最后才说再�?[03:40.67]你送我的眼�?[03:42.24]让它留在雨天
[03:44.56]�?越过你划的线
[03:46.37]我定了勇气的终点
[03:49.01]
[03:49.71]你说我不该不�?[03:51.46]不该在这时候说了我爱你
[03:53.45]要怎么证明我没力气
[03:55.78]可是我只有一天的回忆
[03:57.12]
[03:57.82]你说我不该不�?[03:59.58]不该在这时候才说爱�?[04:01.64]要怎么证明我没力气
[04:03.98]我只有一天的回忆
[04:06.81]~~End~~
*/

import string.lrc;
mainForm.lyric = string.lrc( strLrc );

mainForm.btnPlay.skin({
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

mainForm.show();
return win.loopMessage();

/*
BASS错误代码说明�?------------------------------------
BASS_ERROR_MEM  1   Memory error
BASS_ERROR_FILEOPEN 2   Can't open the file
BASS_ERROR_DRIVER   3   Can't find a free/valid driver
BASS_ERROR_BUFLOST  4   The sample buffer was lost
BASS_ERROR_HANDLE   5   Invalid handle
BASS_ERROR_FORMAT   6   Unsupported sample format
BASS_ERROR_POSITION 7   Invalid playback position
BASS_ERROR_INIT 8   BASS_Init has not been successfully called
BASS_ERROR_START    9   BASS_Start has not been successfully called
BASS_ERROR_NOCD 12  No CD in drive
BASS_ERROR_CDTRACK  13  Invalid track number
BASS_ERROR_ALREADY  14  Already initialized/paused/whatever
BASS_ERROR_NOPAUSE  16  Not paused
BASS_ERROR_NOTAUDIO 17  Not an audio track
BASS_ERROR_NOCHAN   18  Can't get a free channel
BASS_ERROR_ILLTYPE  19  An illegal type was specified
BASS_ERROR_ILLPARAM 20  An illegal parameter was specified
BASS_ERROR_NO3D 21  No 3D support
BASS_ERROR_NOEAX    22  No EAX support
BASS_ERROR_DEVICE   23  Illegal device number
BASS_ERROR_NOPLAY   24  Not playing
BASS_ERROR_FREQ 25  Illegal sample rate
BASS_ERROR_NOTFILE  27  The stream is not a file stream
BASS_ERROR_NOHW 29  No hardware voices available
BASS_ERROR_EMPTY    31  The MOD music has no sequence data
BASS_ERROR_NONET    32  No internet connection could be opened
BASS_ERROR_CREATE   33  Couldn't create the file
BASS_ERROR_NOFX 34  Effects are not available
BASS_ERROR_PLAYING  35  The channel is playing
BASS_ERROR_NOTAVAIL 37  Requested data is not available
BASS_ERROR_DECODE   38  The channel is a 'decoding channel'
BASS_ERROR_DX   39  A sufficient DirectX version is not installed
BASS_ERROR_TIMEOUT  40  Connection timedout
BASS_ERROR_FILEFORM 41  Unsupported file format
BASS_ERROR_SPEAKER  42  Unavailable speaker
BASS_ERROR_VERSION  43  Invalid BASS version (used by add-ons)
BASS_ERROR_CODEC    44  Codec is not available/supported
BASS_ERROR_ENDED    45  The channel/file has ended
BASS_ERROR_BUSY 46  The device is busy (eg. in "exclusive" use by another process)
BASS_ERROR_UNKNOWN  -1  Some other mystery error
BASS_ERROR_WMA_LICENSE  1000    BassWma: the file is protected
BASS_ERROR_WMA_WM9  1001    BassWma: WM9 is required
BASS_ERROR_WMA_DENIED   1002    BassWma: access denied (user/pass is invalid)
BASS_ERROR_WMA_CODEC    1003    BassWma: no appropriate codec is installed
BASS_ERROR_WMA_INDIVIDUAL   1004    BassWma: individualization is needed
BASS_ERROR_ACM_CANCEL   2000    BassEnc: ACM codec selection cancelled
BASS_ERROR_CAST_DENIED  2100    BassEnc: Access denied (invalid password)
BASS_VST_ERROR_NOINPUTS 3000    BassVst: the given effect has no inputs and is probably a VST instrument and no effect
BASS_VST_ERROR_NOOUTPUTS    3001    BassVst: the given effect has no outputs
BASS_VST_ERROR_NOREALTIME   3002    BassVst: the given effect does not support realtime processing
BASS_ERROR_WASAPI   5000    BASSWASAPI: no WASAPI available
BASS_ERROR_MP4_NOSTREAM 6000    BASS_AAC: non-streamable due to MP4 atom order ('mdat' before 'moov')
*/

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/bass.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/bass.md')

