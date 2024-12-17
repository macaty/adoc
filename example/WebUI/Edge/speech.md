[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 语音合成

```aardio aardio
//语音合成
import chrome.edge;
var theApp = chrome.edge.app();

import sys.audioVolume;
var volumeCtrl = sys.audioVolume();

import dotNet.waveIn;
theApp.external = {
    getVolume = function(){
        return volumeCtrl.volume;
    }
    setVolume = function(v){
        v = tonumber(v)
        if(volumeCtrl.volume = v) return;
        volumeCtrl.volume = v;
        volumeCtrl.mute = !v;
    }
    startRecording = function(){
        dotNet.waveIn.startLoopback("/edge.wav");
    }
    stopRecording = function(){
        dotNet.waveIn.stop();
    }
    openWav = function(){
        if(!io.exist("/edge.wav")){
            return theApp.msgboxErr("请先录音");
        }

        process.exploreSelect("/edge.wav")
    }
}

//因为 /res/ 已设�?theApp.http.documentBase，这里不用再�?"/res/index.aardio"
theApp.httpHandler["/index.aardio" ] = function(response,request){
    response.write(`
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Edge 语音合成</title>
    <script src="/aardio.js"></script>
    <style>
        html,
        body {
            height: 100%;
            margin: 0;
        }
    </style>
</head>
<body style="margin:0;line-height:180%;height:100%">
    <form
        style="height:100%;display:flex;flex-direction:column;justify-content:flex-start;align-content:stretch;padding:15px;box-sizing:border-box">
        <div style="flex:0 1 auto;">
            <label>请选择语音�?select> </select></lable><br>
                <label for="volume">系统音量:<input type="range" min="0" max="100" step="1" id="volume"><span
                        class="volume-value">1</span></label>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                <label for="rate">速度:<input type="range" min="0.5" max="2" value="1" step="0.1" id="rate"><span
                        class="rate-value">1</span></label>
                &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
                <label for="pitch">音调:<input type="range" min="0" max="2" value="1" step="0.1" id="pitch"> <span
                        class="pitch-value">1</span></label>
        </div>

        <div class="controls" style="flex:0 1 auto;">
            <button id="play" type="submit" style="margin-top:5px">大声朗读下面输入的文�?/button> <label><input type="checkbox"
                    id="recording">录音�?<a href="javascript:void(0)" onclick="aardio.openWav()">/edge.wav</a></label>
        </div>

        <textarea rows="20" cols="100" id="txt" name="txt" autofocus
            style="margin-top:10px;width:100%;flex:1 1 auto;"></textarea>

    </form>

    <script>
        var synth = window.speechSynthesis;

        var inputForm = document.querySelector('form');
        var inputTxt = document.querySelector('#txt');
        var voiceSelect = document.querySelector('select');

        var volume = document.querySelector('#volume');
        var volumeValue = document.querySelector('.volume-value');
        var pitch = document.querySelector('#pitch');
        var pitchValue = document.querySelector('.pitch-value');
        var rate = document.querySelector('#rate');
        var rateValue = document.querySelector('.rate-value');

        var voices = [];

        function populateVoiceList() {
            voices = synth.getVoices().sort(function (a, b) {
                const aname = a.name.toUpperCase(), bname = b.name.toUpperCase();
                if (aname < bname) return -1;
                else if (aname == bname) return 0;
                else return +1;
            });

            voiceSelect.innerHTML = '';

            var selectedIndex = 0;
            var voiceCount = 0;
            for (i = 0; i < voices.length; i++) {
                var option = document.createElement('option');
                if (voices[i].name.indexOf("Chinese") < 0) {
                    continue;
                }
                option.textContent = voices[i].name + ' (' + voices[i].lang + ')';

                if (voices[i].default) {
                    option.textContent += ' -- DEFAULT';
                }

                option.setAttribute('data-lang', voices[i].lang);
                option.setAttribute('data-name', voices[i].name);
                if (voices[i].name.indexOf("Xiaoxiao") > 0) {
                    selectedIndex = voiceCount;
                }
                voiceSelect.appendChild(option);
                voiceCount++;
            }
            voiceSelect.selectedIndex = selectedIndex;
        }

        populateVoiceList();
        if (speechSynthesis.onvoiceschanged !== undefined) {
            speechSynthesis.onvoiceschanged = populateVoiceList;
        }

        function speak2() {
            var txt = inputTxt.value;
            if (txt === '') txt = "请先输入要朗读的文本";
            document.getElementById("play").disabled = true;

            var utterThis = new SpeechSynthesisUtterance(txt);
            utterThis.onend = function (event) {
                document.getElementById("play").disabled = false;
                aardio.stopRecording();
            }
            utterThis.onerror = function (event) {
                document.getElementById("play").disabled = false;
            }
            var selectedOption = voiceSelect.selectedOptions[0].getAttribute('data-name');
            for (i = 0; i < voices.length; i++) {
                if (voices[i].name === selectedOption) {
                    utterThis.voice = voices[i];
                    break;
                }
            }
            utterThis.pitch = pitch.value;
            utterThis.rate = rate.value;
            synth.speak(utterThis);
        }

        function speak() {
            if (synth.speaking) {
                console.error('speechSynthesis.speaking');
                return;
            }

            if (document.getElementById("recording").checked) {
                aardio.startRecording().then(speak2)
            }
            else {
                speak2();
            }
        }

        inputForm.onsubmit = function (event) {
            event.preventDefault();

            speak();

            inputTxt.blur();
        }

        pitch.onchange = function () {
            pitchValue.textContent = pitch.value;
        }

        rate.onchange = function () {
            rateValue.textContent = rate.value;
        }

        volume.onchange = function () {
            volumeValue.textContent = volume.value;
            aardio.setVolume(volume.value);
        }

        aardio.getVolume().then(v => { volume.value = v; volume.onchange() })

        voiceSelect.onchange = function () {
            //speak();
        }
    </script>
</body>
</html>`)
}

//此函数参数指定的回调函数会在网页端准备就绪后执行
theApp.indexReady(
    function($){ //参数 $ 表示当前连接�?aardio 的网页客户端
        theApp.doScript($,`
            document.getElementById("txt").innerText = "这是测试文本";
        `)
    }
)

//可选在调用 start 函数前用 theApp.setPos �?theApp.center 调整窗口位置
theApp.setPos(20,20,1080,720)

/*
正式启动 Edge 进程�?如果文件名为 index.html �?index.aardio，目�?"/res/" 会自动设�?theApp.http.documentBase�?之后网页访问 "/index.aardio" 会自动转�?"/res/index.aardio" �?*/
theApp.start("/res/index.aardio")

//网页中可以调�?aardio.quit() 退�?也可以直接关�?Edge 窗口退�?win.loopMessage();

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/WebUI/Edge/speech.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/WebUI/Edge/speech.md')

