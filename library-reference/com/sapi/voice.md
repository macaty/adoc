[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# com.sapi.voice 库模块帮助文�?
## com.sapi 成员列表

### com.sapi.voice

SAPI语音对象,

SAPI为正常系统自带组件，如果是精简过删除了SAPI组件的系统请自行安装修复该组�?
### com.sapi.voice()

创建SAPI语音对象

[返回对象:comsapivoiceObject](#comsapivoiceObject)

## comsapivoiceObject 成员列表

### comsapivoiceObject.displayUI(hWndParent,title,typeOfUI,extraData)

显示指定界面

### comsapivoiceObject.eachVoices()

```aardio aardio
for name,lang,gender,age,vendor,description in comsapivoiceObject.eachVoices(){
    /*遍历所有语音库,
name为名�?lang为语言代码,gender为性别,age为年�?vendor为厂�?description为详细说�?/
}

```

### comsapivoiceObject.event

回调事件�?
[返回对象:comsapivoiceeventObject](#comsapivoiceeventObject)

### comsapivoiceObject.getStatus()

返回当前状�?
[返回对象:comsapivoicestatusObject](#comsapivoicestatusObject)

### comsapivoiceObject.getVoicesEx()

返回数组,数组由所有语音库的属性列表组�?
如果在参数中使用一个字符串参数指定要返回的属�?

则返回由所有语音库的对应属性值组成的数组

### comsapivoiceObject.isUiSupported(typeOfUI,extraData)

是否支持指定界面

### comsapivoiceObject.pause()

暂停朗读

### comsapivoiceObject.rate

说话速度，值范围从 -10�?0

### comsapivoiceObject.resume()

继续朗读

### comsapivoiceObject.setVoice()

设置当前语音�?
### comsapivoiceObject.setVoiceByAttributes(必需属�?可选属�?

使用属性设置语音库

属性使�?Attribute = Value"或�?Attribute != Value" 格式的字符串表示

### comsapivoiceObject.setVoiceByIndex()

使用索引设置语音�?
### comsapivoiceObject.setVoiceByLanguage()

使用语言代码设置语音�?
804 表示中文,409表示英文

### comsapivoiceObject.setVoiceByName()

使用名称设置语音�?
### comsapivoiceObject.skip(type,numItems)

跳过指定的文�?
### comsapivoiceObject.speak(text,flags)

朗读,text参数指定要朗读的字符�?
flags为可选参�?可指定如下值：

SVSFDefault = 0

SVSFlagsAsync = 1

SVSFPurgeBeforeSpeak = 2

SVSFIsFilename = 4

SVSFIsXML = 8

SVSFIsNotXML = 16

SVSFPersistXML = 32

SVSFNLPSpeakPunc = 64

SVSFNLPMask = 64

SVSFVoiceMask = 127

SVSFUnusedFlags = -128

### comsapivoiceObject.speakAsync(text,flags)

异步非阻塞朗�?text参数指定要朗读的字符�?
flags为可选参�?参考speak函数flags参数的说�?
此函数与speak用法相同,但flags默认指定了SVSFlagsAsync选项

### comsapivoiceObject.speakCompleteEvent()

返回一个用于等待的事件句柄,

可作�?thread.waitOne 的参数使�?
### comsapivoiceObject.speakStream(stream,flags)

朗读文件流，例如SAPI.SpFileStream

### comsapivoiceObject.speakXml(text,flags)

异步非阻塞朗读XML格式文本,text参数指定要朗读的字符�?
flags为可选参�?参考speak函数flags参数的说�?
此函数与speak用法相同,但flags默认指定了SVSFlagsAsync,SVSFIsXML选项

### comsapivoiceObject.status

当前状�?
[返回对象:comsapivoicestatusObject](#comsapivoicestatusObject)

### comsapivoiceObject.voice

当前语音�?
### comsapivoiceObject.volume

音量，值范围从 0�?00

### comsapivoiceObject.waitOne()

异步朗读�?可使用此函数等待朗读结束

### comsapivoiceObject.waitUntilDone(\_)

等待直到完成,参数指定超时,超时指定�?1表示直到朗读完成

## comsapivoiceeventObject 成员列表

### comsapivoiceeventObject.AudioLevel

```aardio aardio
comsapivoiceeventObject.AudioLevel = function(streamNumber,streamPosition,audioLevel){
    /*音频变化触发*/
}

```

### comsapivoiceeventObject.EndStream

```aardio aardio
comsapivoiceeventObject.EndStream = function(streamNumber ,streamPosition){

}

```

### comsapivoiceeventObject.EnginePrivate

```aardio aardio
comsapivoiceeventObject.EnginePrivate =  function(streamNumber,streamPosition,engineData){

}

```

### comsapivoiceeventObject.Phoneme

```aardio aardio
comsapivoiceeventObject.Phoneme =  function(streamNumber, streamPosition,Duration,nextPhoneId,Feature,currentPhoneId){
   /*新的音素*/
}

```

### comsapivoiceeventObject.Sentence

```aardio aardio
comsapivoiceeventObject.Sentence =  function(streamNumber,streamPosition,characterPosition,length){
   /*新的句子*/
}

```

### comsapivoiceeventObject.StartStream

```aardio aardio
comsapivoiceeventObject.StartStream = function(streamNumber,streamPosition ){

}

```

### comsapivoiceeventObject.Viseme

```aardio aardio
comsapivoiceeventObject.Viseme =  function(streamNumber,streamPosition,duration,nextVisemeId,feature,currentVisemeId){
   /*新的嘴形*/
}

```

### comsapivoiceeventObject.VoiceChange

```aardio aardio
comsapivoiceeventObject.VoiceChange =  function(streamNumber,streamPosition ,voiceObjectToken ){
    var v = voiceObjectToken.GetDescription();
}

```

### comsapivoiceeventObject.Word

```aardio aardio
comsapivoiceeventObject.Word =  function(streamNumber,streamPosition,characterPosition,length ){
   /*一个新单词开�?/
}

```

## comsapivoicestatusObject 成员列表

### comsapivoicestatusObject.currentStreamNumber

输入流数�?

### comsapivoicestatusObject.inputSentenceLength

当前语句长度

### comsapivoicestatusObject.inputSentencePosition

当前语句开始位�?
### comsapivoicestatusObject.inputWordLength

当前朗读的单词长�?
### comsapivoicestatusObject.inputWordPosition

当前朗读的单词开始位�?
### comsapivoicestatusObject.lastBookmark

最后一个书签的字符串�?
### comsapivoicestatusObject.lastBookmarkId

最后一个书签的ID

### comsapivoicestatusObject.lastHResult

最后一次调用speak,speakStream的状态码

### comsapivoicestatusObject.lastStreamNumberQueued

朗读的最后一个音频流编号

### comsapivoicestatusObject.phonemeId

当前音素ID

### comsapivoicestatusObject.runningState

当前朗读状�?
SRSEIsSpeaking 值为2 表示正在朗读

SRSEDone 值为1表示朗读已完�?
### comsapivoicestatusObject.visemeId

当前口形ID

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/com/sapi/voice.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/com/sapi/voice.md')

