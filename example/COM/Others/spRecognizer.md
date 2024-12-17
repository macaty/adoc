[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: COM 鎺ュ彛 - 璋冪敤 SpInprocRecognizer

```aardio aardio
//COM 鎺ュ彛 - 璋冪敤 SpInprocRecognizer

import win.ui;
/*DSG{{*/
var winform = win.form(text="璋冪敤SpInprocRecognizer";right=599;bottom=399)
winform.add(
edit={cls="edit";left=21;top=19;right=583;bottom=374;edge=1;multiline=1;z=1}
)
/*}}*/

var spRecognizer = com.CreateObject("SAPI.SpInprocRecognizer" )
spRecognizer.AudioInput = spRecognizer.GetAudioInputs().Item(0);

var recoContext = spRecognizer.CreateRecoContext();
var dicGrammar =  recoContext.CreateGrammar();
dicGrammar.DictationSetState(spRecognizer.SGDSActive);

var menuRule = dicGrammar.Rules.Add("wordsRule", 0x1|0x20)
menuRule.Clear();
menuRule.InitialState.AddWordTransition(null, "浣犲ソ", " ", spRecognizer.SGLexical, "浣犲ソ", 1, "", 1.0);
dicGrammar.CmdSetRuleState("wordsRule", spRecognizer.SGDSActive)
dicGrammar.Rules.Commit()

RecognitionEvents = {

    Recognition = function(streamNumber,streamPosition,recogType,recoResult) {
           var text = recoResult.PhraseInfo.GetText()
           winform.edit.log("璇嗗埆瀹屾垚:",text ,'\r\n' )
    }

    Hypothesis = function(streamNumber , streamPosition, recoResult){
        for index,el in com.each(recoResult.PhraseInfo.Elements) {
            winform.edit.log(el.DisplayText ,'\r\n' )
        }
    }
}
//娣诲姞浜嬩欢瑙﹀彂鍣?com.Connect(recoContext, RecognitionEvents  )

winform.show()
recoContext.Voice.Speak("浣犲ソ");

win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/COM/Others/spRecognizer.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/COM/Others/spRecognizer.md')

