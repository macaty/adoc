[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 使用SAPI语音组件朗读文本示例

```aardio aardio
//SAPI 文本转语�?import win.ui;
/*DSG{{*/
var winform = win.form(text="使用SAPI语音组件朗读文本示例";right=825;bottom=532)
winform.add(
button={cls="button";text="朗读";left=657;top=429;right=780;bottom=468;db=1;dr=1;z=1};
cbVoice={cls="combobox";left=379;top=436;right=639;bottom=462;db=1;dl=1;dr=1;edge=1;items={};mode="dropdown";z=2};
edit={cls="edit";left=20;top=9;right=794;bottom=426;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=8};
lbRate={cls="static";text="语�?";left=53;top=498;right=120;bottom=520;align="right";db=1;dl=1;transparent=1;z=6};
lbVolume={cls="static";text="音量:";left=372;top=498;right=434;bottom=520;align="right";db=1;dl=1;dr=1;transparent=1;z=5};
plusAudioLevel={cls="plus";left=795;top=9;right=813;bottom=423;bgcolor=10789024;db=1;dr=1;dt=1;z=3};
tbRate={cls="trackbar";left=149;top=487;right=375;bottom=517;db=1;dl=1;max=100;min=0;z=7};
tbVolume={cls="trackbar";left=467;top=487;right=693;bottom=517;db=1;dr=1;max=100;min=0;z=4}
)
/*}}*/

winform.edit.text = /*<lang langid='409'>Hello</lang>
<lang langid='804'>你好</lang>
<VOLUME LEVEL='90'>SAPI为正常系统自带组件，如果是精简过删除了SAPI组件的系统请自行安装修复该组�?/VOLUME>
*/

import com.sapi.voice;//导入语音组件
var voice = com.sapi.voice();//创建语音对象

//设置plus控件的进度条效果,用于显示音频变化
winform.plusAudioLevel.foreground = 0xFFE5f897;
winform.plusAudioLevel.setProgressRange(0,50);
voice.event.AudioLevel = function(streamNumber,streamPosition,audioLevel){
winform.plusAudioLevel.progressPos = audioLevel;
}

//随着朗读的进度，自动选中正在朗读的词,
voice.event.Word =  function(streamNumber,streamPosition,characterPosition,length ){
    characterPosition++;
    winform.edit.setsel(characterPosition,characterPosition + length-1);
    //注意richedit会自动将\r\n转换为\n显示,所以改用edit控件这里的字符位置就是完全一致的
}

//列出系统支持的所有语音库
for name,lang,gender,age,vendor,description in voice.eachVoices(){
     winform.cbVoice.add(description);
     if(lang==804){
         winform.cbVoice.selIndex = winform.cbVoice.count;
     }
}

//开始朗�?winform.button.oncommand = function(id,event){
    winform.button.disabledText = "正在朗读...";

    voice.volume = winform.tbVolume.pos;//音量
    voice.rate = winform.tbRate.pos;//语�?
    voice.setVoiceByIndex(winform.cbVoice.selIndex);//语音�?    voice.speakAsync(winform.edit.text,1);//异步非阻塞朗�?    voice.waitOne();//等待朗读结束

    winform.button.disabledText = null;
}

//语速滑�?winform.tbRate.setRange(-10,10);
winform.tbRate.pos = voice.rate;

//音量滑块
winform.tbVolume.setRange(0,100);
winform.tbVolume.pos = voice.volume;

winform.show()
win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Media/Audio/tts.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Media/Audio/tts.md')

