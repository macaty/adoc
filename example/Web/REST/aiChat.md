[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: AI 聊天助手

```````aardio aardio
import win.ui;
import fonts.fontAwesome;
/*DSG{{*/
var winform = win.form(text="aardio - AI 聊天助手";right=759;bottom=607)
winform.add(
btnClear={cls="plus";text="清除";left=589;top=572;right=655;bottom=602;align="left";color=3947580;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF014';notify=1;textPadding={left=25};z=6};
btnCopy={cls="plus";text="复制";left=202;top=572;right=269;bottom=602;align="left";color=3947580;db=1;disabled=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF0EA';notify=1;textPadding={left=25};z=11};
btnSend={cls="plus";text="�?AI";left=660;top=572;right=732;bottom=602;align="left";color=3947580;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF007';notify=1;textPadding={left=25};z=5};
btnSetting={cls="plus";text="设置";left=513;top=572;right=580;bottom=602;align="left";color=3947580;db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF013';notify=1;textPadding={left=25};z=7};
chkFix={cls="plus";text="更正";left=276;top=572;right=336;bottom=603;align="left";db=1;dr=1;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-14;name='FontAwesome')};iconText='\uF0C8 ';notify=1;textPadding={left=24};z=12};
editMaxTokens={cls="edit";left=427;top=577;right=470;bottom=600;align="right";db=1;dr=1;edge=1;z=9};
editPrompt={cls="richedit";left=11;top=452;right=754;bottom=567;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=2};
promptTool={cls="syslink";text="提示词生成器 / AI 搜索";left=20;top=577;right=163;bottom=600;center=1;db=1;dl=1;notify=1;z=4};
spinMaxTokens={cls="spin";left=471;top=578;right=491;bottom=600;db=1;dr=1;z=8};
splitter={cls="splitter";left=8;top=453;right=751;bottom=458;db=1;dl=1;dr=1;frame=1;horz=1;z=3};
static={cls="static";text="回复长度�?;left=352;top=575;right=418;bottom=598;align="right";center=1;db=1;dr=1;transparent=1;z=10};
wndBrowser={cls="custom";text="自定义控�?;left=8;top=5;right=751;bottom=447;db=1;dl=1;dr=1;dt=1;z=1}
)
/*}}*/

//创建显示聊天消虑�?Web 浏览器窗�?import web.form.chat;
var wb = web.form.chat(winform.wndBrowser);

import fsys.table;
var config = fsys.table(io.appData("aardio/ide/aiChat/~"))

var systemPrompt = /****************
## 角色

你是 aardio 编程助手，擅�? aardio 编程�?
## 任务

你会解答  aardio 编程问题，并且帮助用户生成或改进 aardio 代码�?
## aardio 语法要求

- 使用 `{}` 标记语句块�?- 使用 `{}` 构造器创建表（对象或数组），例�?`var arr = {1,2,3}`�?- 数组起始索引�?1 �?- 只能使用 var 声明局部变量�?- 使用 `++` 连接字符串�?- 函数默认参数只能定义为布尔值、字符串、数值之一�?- 双引号包含的是原始字符串，不处理转义符�?- aardio 默认使用模式匹配语法代替正则表达式�?    - 模式匹配使用尖括号`<>`包含非捕获组�?    - 非捕获组内部不能包含捕获组�?    - 只能对单个字符或非捕获组可以使用模式运算符（例如量词），不能对捕获组使用模式运算符�?    - 用双引号包含模式串，模式转义符应当写为单个反斜杆而不是双反斜杆，例如 `"\d"` 不能写为  `"\\d"`�?
## for 循环语句格式

```aardio
for(i = initialValue;finalValue;incrementValue){
    // code block to be executed
}
```

- aardio 使用基于数值范围的 for 循环，全部循环参数都必须是数值表达式，没有`条件（condition-expression）`与`迭代（iteration-expression）`部分�?- 循环数值范围自 initialValue 开始到 finalValue 结束，finalValue 必须是确定的数值�?- 循环增量 incrementValue 必须是数值�?
示例�?
```aardio

//声明数组
var arr = {1,2,3}

//循环遍历数组�?arr 取数组长�?for(i=1;#arr;1){
    print(arr[i]);//循环输出所有数组成�?}
```

## import 语句要求

- aardio 中除 raw,string,table,math,io,time,thread 等无需导入的内置库以外，其他所有库（标准库或扩展库）都必须先用 import 语句导入后才能使用�?- 如果代码中用到了 `win.form` 则必须使�?`import win.ui` 导入 win.form 窗口�?�?- 如果代码中需要操�?JSON，则必须使用 `import web.json` 导入 web.json 库�?
## 窗口程序示例

```aardio
import win.ui;
/*DSG{{*/
var winform = win.form({text="第一�?aardio 窗口程序"})
winform.add({
button={cls="button";text="点这�?;note="这是一个很酷的按钮";left=435;top=395;right=680;bottom=450;color=14120960;z=2};
edit={cls="edit";left=18;top=16;right=741;bottom=361;edge=1;multiline=1;z=1}
})
/*}}*/

//按钮回调事件
winform.button.oncommand = function(){

    //修改控件属�?    winform.edit.text = "Hello, World!";

    //输出字符串或对象，自动添加换�?    winform.edit.print(" 你好�?);

    //创建工作线程
    thread.invoke(
        function(winform){

            //每个线程使用隔离的变量环境，线程使用的库必须单独导入
            import web.rest.jsonLiteClient;

            //创建 HTTP 客户端，响应数据格式�?JSON，提交数据格式为 Url Encoded。如果提交与响应格式都是 JSON 请改�?web.rest.jsonClient �?            var http = web.rest.jsonLiteClient();

            //声明 HTTP API 对象�?            var delivery = http.api("https://api.pi.delivery/v1/pi");

            //使用 "GET" 方法发送请求并查询圆周率，参数指定一个表对象（table），单个表参数外层的 {} 也可以省略不�?            var ret = delivery.get({
                start=1, //从第 1 位开�?                numberOfDigits=100 //返回 100 位圆周率
            })

            //在工作线程中调用界面控件的属性与方法会自动转发到界面线程执行�?            winform.edit.print("圆周率：" ,"3."+ ret.content);

        },winform //线程函数都是纯函数，外部线程的对象必须通过参数传入线程
    )
}

//显示窗口
winform.show();

//启动界面线程的消息循�?win.loopMessage();
```

## 调用 web.view 的网页界面示�?
```aardio
import win.ui;
var winform = win.form(text="WebView2"); //创建窗口

import web.view;
var wb = web.view(winform);//在宿主窗�?winform 内创�?WebView2 浏览器窗�?
//导出 aardio 对象�?JavaScript �?wb.external = {
    getNativeObject = function(){
        return {prop1=123;prop2="NativeObject value"}
    };
}

//导出 aardio 函数�?JavaScript 全局函数�?wb.export({
    getJsonObject = function(){
        return {prop1=123;prop2="JsonObject value"}
    }
})

//写入网页
wb.html = /**
<!doctype html>
<html><head>
<script>
(async()=>{

    //�?JavaScript 内调�?wb.externa 导出�?aardio 对象�?    var nativeObject = await aardio.getNativeObject(); //返回基于 COM 接口的对象�?
    //nativeObject 的属性与方法都是 Promise
    var prop2 = await nativeObject.prop2;

    //调用 wb.export 导出�?aardio 函数，参数与返回值通过 JSON 转换
    var jsonObject = await getJsonObject()

    // jsonObject 是纯 JavaScript 对象
    alert( jsonObject.prop2 )
})()
</script>
**/

winform.show();
win.loopMessage();
****************/

//清除上下�?var resetMessages = function(){

    wb.clear();

    var p = systemPrompt;

    if(config.quickRef){
        p = p + '\r\n\r\n---\r\n\r\n' + string.load("~\doc\guide\language\syntax-quick-ref.md");
    }

    //输入系统提示�?    wb.system(  p );
}

resetMessages();

winform.btnClear.oncommand = function(id,event){
    resetMessages();//清除聊天上下�?}

//响应按键事件，输入用户提示词
winform.btnSend.oncommand = function(id,event){

    //按钮显示等待动画
    winform.btnSend.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250'}
    winform.btnClear.disabled = true;
    winform.btnCopy.disabled = true;
    winform.chkFix.disabled = true;

    wb.limit = config.msgLimit;

    var assistantMsg = wb.lastAssistantMessage();
    if(assistantMsg && winform.chkFix.checked){
        //Few-shot Learning
        assistantMsg.content = ide.aifix.markdown(assistantMsg.content,true);
    }

    var prompt = winform.editPrompt.text;

    var knowledge = ""
    prompt = string.replace(prompt,"(https?\://<www\.>?aardio\.com/zh\-cn/doc/\S+)\.<html>|<md>",
        function(url){

            url = url + ".md";
            wb.showLoading("正在读取�?+url)

            var md = inet.http.get(url);
            if(md){
                md = '\r\n\r\n用户输入的参考网址�? + url
                    +  '\r\n\r\n下面是自该网址获取�?Markdown 格式文档或范例：'
                    +  '\r\n\r\n' + md +'\r\n\r\n------------------------\r\n\r\n'

                knowledge = knowledge + md;

            }
        });

    if(#knowledge){
        wb.system(knowledge)
    }

    //输入 AI 提示�?    wb.prompt( prompt );

    config.maxTokens = winform.spinMaxTokens.pos;

    //创建多线程向服务端发送请�?    thread.invoke(
        function(wb,config){

            for(k,v in config){
                if(v=="")config[k] = null;
            }

            config = table.mix(config,{
                /*
                下面�?key 24 小时后失效，
                DeepSeek �?key �?10 元估计能用上一年，所以请自己申请一个好吗？�?                */
                key = "sk-2f729981180a45e3b28971e9a5c68c72";
                url = "https://api.deepseek.com/v1";
                model = "deepseek-chat";
                temperature = 0.1;
            });

            if(config.maxTokens>1024 && (config.key === "sk-2f729981180a45e3b28971e9a5c68c72" ) ){
                wb.errorMessage(`回复长度超过 1024 时，必须更改为您自己�?API 密钥 �?a href="https://platform.deepseek.com">点这里获取密�?/a>�?nbsp;<a href="javascript:void(0)" onclick="javascript:external.updateApiKey()">点这里设置新密钥</a>。`);
                return;
            }

            //导入调用 HTTP 接口�?REST 客户�?            import web.rest.aiChat;
            var client = web.rest.aiChat(config);

            var ok,err = client.messages(wb.chatMessage,function(deltaText){
                wb.assistant(deltaText);
            } );

            if(err){
                //获取错误对象（解�?JSON 格式的错误信息）
                var errObject = client.lastResponseError()
                if(errObject[["error"]][["type"]] == "authentication_error" ){
                    wb.errorMessage(`API 密钥错误�?a href="https://platform.deepseek.com">点这里获取密�?/a>�?nbsp;<a href="javascript:void(0)" onclick="javascript:external.updateApiKey()">点这里设置新密钥</a>`)
                }
                else {
                    wb.errorMessage(err)
                }
            }

        },wb,config//将参数传入线�?    )
}

//�?AI 回复结束后回调此函数
wb.onWriteEnd = function(){
    winform.btnSend.disabledText = null;//关闭等待动画
    winform.btnClear.disabled = false;
    winform.btnCopy.disabled = false;
    winform.chkFix.disabled = false;
}

//�?AI 回复结束以前回调此函数，自动修正 aardio 代码块中的常见幻觉错�?import ide.aifix;
wb.beforerWriteEnd = function(markdown){
    if(winform.chkFix.checked) return ide.aifix.markdown(markdown,true);
    return markdown;
}

//导出 aardio 函数到网�?JavaScript 中�?wb.external = {
    updateApiKey = function(){
        winform.btnSetting.oncommand();
    }
}

import key;
import win.clip;
winform.btnCopy.oncommand = function(id,event){
    var md = wb.lastMarkdown();
    if(!#md) return winform.msgboxErr("消息为空�?);

    if(key.getState("CTRL")){

        var found;
        for indent,_,code in string.gmatch(md,"!\N([ \t]*)(```+)<aardio>(.+?)!\N\s*\2![^`\S]") {

            if(#indent){
                text = string.replace(text,"\n+"+indent,'\n');
            }

            if(winform.chkFix.checked) code = ide.aifix(code,true);
            win.clip.write( code );
            found = true;
        }

        if(!found){
            return winform.msgboxErr("没有找到代码块�?);
        }
    }
    else{
        if(winform.chkFix.checked) md = ide.aifix.markdown(md,true);
        win.clip.write( md )
    }

    winform.btnCopy.disabledText = {'\uF254';'\uF251';'\uF252';'\uF253';'\uF250';text=''}
    thread.delay(600);
    winform.btnCopy.disabledText = null;
}

//设置接口地址�?API 令牌的窗�?winform.btnSetting.oncommand = function(id,event){
    var frmSetting = win.form(text="aardio - 设置 AI 聊天助手";right=684;bottom=363;border="dialog frame";exmode="none";max=false;min=false;mode="popup")
    frmSetting.add(
        btnAdd={cls="plus";left=18;top=235;right=52;bottom=265;align="left";color=3947580;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF067';notify=1;textPadding={left=25};z=12};
        btnEdit={cls="plus";left=93;top=235;right=127;bottom=265;align="left";color=3947580;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF044';notify=1;textPadding={left=25};z=14};
        btnRemove={cls="plus";left=56;top=235;right=90;bottom=265;align="left";color=3947580;font=LOGFONT(h=-13);iconStyle={align="left";font=LOGFONT(h=-13;name='FontAwesome');padding={left=8}};iconText='\uF1F8';notify=1;textPadding={left=25};z=13};
        btnSave={cls="button";text="更新配置";left=458;top=298;right=628;bottom=343;z=5};
        chkQuickRef={cls="checkbox";text="新建会话自动发送语法速览（约 8k tokens�?;left=18;top=287;right=272;bottom=309;z=15};
        editApiKey={cls="edit";left=284;top=104;right=662;bottom=131;edge=1;password=1;z=2};
        editApiUrl={cls="combobox";left=284;top=31;right=662;bottom=57;edge=1;items={};mode="dropdown";z=20};
        editModel={cls="edit";left=284;top=68;right=662;bottom=95;edge=1;z=7};
        editProxy={cls="edit";left=283;top=223;right=661;bottom=250;edge=1;z=21};
        groupbox={cls="groupbox";text="选择当前配置�?;left=9;top=6;right=675;bottom=270;edge=1;z=1};
        lbMsgLimit={cls="static";left=390;top=315;right=418;bottom=335;transparent=1;z=18};
        lbTemperature={cls="static";left=633;top=140;right=659;bottom=160;transparent=1;z=19};
        lstConfig={cls="listbox";left=18;top=34;right=187;bottom=235;edge=1;hscroll=1;items={};vscroll=1;z=11};
        static={cls="static";text="模型 ID�?;left=196;top=72;right=279;bottom=93;align="right";transparent=1;z=3};
        static2={cls="static";text="API key�?;left=196;top=107;right=279;bottom=128;align="right";transparent=1;z=4};
        static3={cls="syslink";text='推荐使用 Claude 3.5 Sonnet �?<a href="https://platform.deepseek.com">DeepSeek</a> 。\n模型 ID 前加 @ 使用 Anthropic 接口，否则使�?OpenAI 接口�?;left=283;top=176;right=653;bottom=224;transparent=1;z=6};
        static4={cls="static";text="接口地址�?;left=196;top=38;right=279;bottom=59;align="right";transparent=1;z=8};
        static5={cls="static";text="temperature�?;left=196;top=141;right=279;bottom=162;align="right";transparent=1;z=10};
        static6={cls="static";text="上下文轮数：";left=0;top=321;right=95;bottom=353;align="right";transparent=1;z=17};
        static7={cls="static";text="代理服务器：";left=196;top=227;right=279;bottom=248;align="right";transparent=1;z=22};
        tbMsgLimit={cls="trackbar";left=99;top=313;right=382;bottom=343;max=100;min=0;z=16};
        tbTemperature={cls="trackbar";left=283;top=137;right=633;bottom=167;max=100;min=0;z=9}
    )

    frmSetting.editProxy.setCueBannerText("socks=127.0.0.1:1081")

    frmSetting.editApiUrl.items = {
        "https://api.deepseek.com/v1",
        "https://api.anthropic.com/v1",
        "https://generativelanguage.googleapis.com/v1beta",
        "https://api.x.ai/v1",
        "https://api.openai.com/v1"
    }

    frmSetting.editApiUrl.onListChange = function(){
        var url = frmSetting.editApiUrl.selText;
        if(url=="https://api.deepseek.com/v1"){
            frmSetting.editModel.text = "deepseek-chat"
        }
        elseif(url=="https://api.anthropic.com/v1"){
            frmSetting.editModel.text = "@claude-3-5-sonnet-latest"
        }
        elseif(url=="https://generativelanguage.googleapis.com/v1beta"){
            frmSetting.editModel.text = "gemini-2.0-flash-exp"
        }
        elseif(url=="https://api.x.ai/v1"){
            frmSetting.editModel.text = "grok-beta"
        }
        elseif(url=="https://api.openai.com/v1"){
            frmSetting.editModel.text = "chatgpt-4o-latest"
        }
    }

    frmSetting.tbMsgLimit.setRange(3,100);
    frmSetting.tbTemperature.setRange(0,10);
    frmSetting.tbTemperature.oncommand = function(id,event,pos){

        var pos = frmSetting.tbTemperature.pos;
        frmSetting.tbTemperature.tooltip = pos / 10;
        frmSetting.lbTemperature.text = pos / 10;
    }

    frmSetting.tbMsgLimit.oncommand = function(id,event,pos){

        frmSetting.lbMsgLimit.text = frmSetting.tbMsgLimit.pos;;
    }

    import win.ui.listEdit;
    var listEdit = win.ui.listEdit(frmSetting.lstConfig);
    listEdit.editBox.setCueBannerText("请输入配置名",true);

    if(!#config.itemNames) {
        config.itemNames = {"默认"}
        config.itemData = {{
            url = config.url || "https://api.deepseek.com/v1";
            key = config.key;
            model = #config.model ? config.model : "deepseek-chat";
            temperature = config.temperature;
        }};
    }

    frmSetting.lstConfig.onSelChange = function(){
        var selIndex = frmSetting.lstConfig.selIndex;

        if(config.selItem && config.selItem != selIndex){
            //保存上一个配�?            var configItem = {
                url = frmSetting.editApiUrl.text;
                key = frmSetting.editApiKey.text;
                model = frmSetting.editModel.text;
                temperature = frmSetting.tbTemperature.pos / 10;
                msgLimit = frmSetting.tbMsgLimit.pos;
                proxy = string.trim(frmSetting.editProxy.text);
            }

            config.itemData[config.selItem] = configItem;
        }

        //加载下一个配�?        var selIndex = frmSetting.lstConfig.selIndex;
        var configItem = config.itemData[selIndex] || {};

        frmSetting.editApiUrl.text = configItem.url;
        frmSetting.editApiKey.text = configItem.key;
        frmSetting.editProxy.text = configItem.proxy;

        if(configItem.temperature===null) configItem.temperature = 0.1;
        frmSetting.tbTemperature.pos = configItem.temperature * 10;
        frmSetting.tbTemperature.tooltip = configItem.temperature;
        frmSetting.lbTemperature.text = configItem.temperature;

        frmSetting.tbMsgLimit.pos = configItem.msgLimit || 15;
        frmSetting.lbMsgLimit.text = configItem.msgLimit || 15;

        frmSetting.editModel.text = configItem.model;

        config.proxy = null;
        table.assign(config,configItem);

        config.itemData[selIndex] = configItem;
        config.itemNames = frmSetting.lstConfig.items;
        config.itemData = table.slice(config.itemData,1,#config.itemNames);
        config.selItem = selIndex;

        config.save();
    }

    frmSetting.lstConfig.items = config.itemNames;
    frmSetting.lstConfig.selIndex = config.selItem || 1;
    frmSetting.lstConfig.onSelChange();
    frmSetting.chkQuickRef.checked = config.quickRef;

    frmSetting.editModel.onChange = function(){
         if(string.find(owner.text,"<grok\-beta>")){
            frmSetting.chkQuickRef.checked = true;
         }
    }

    //保存并更新配�?    import inet.url;
    frmSetting.btnSave.oncommand = function(id,event){

        var configItem = {
            url = frmSetting.editApiUrl.text;
            key = frmSetting.editApiKey.text;
            model = frmSetting.editModel.text;
            temperature = frmSetting.tbTemperature.pos / 10;
            msgLimit = frmSetting.tbMsgLimit.pos;
            proxy = string.trim(frmSetting.editProxy.text);
        }

        if(!#configItem.proxy){
            configItem.proxy = null;
        }

        var tUrl = inet.url.split(configItem.url);
        if(tUrl[["host"]]=="api.anthropic.com"){
            if(configItem.model[1]!='@'#){
                configItem.model = '@' + configItem.model;
            }
        }
        elseif(tUrl[["host"]]=="generativelanguage.googleapis.com"){
            configItem.url = "https://generativelanguage.googleapis.com/v1beta"
        }

        var selIndex = frmSetting.lstConfig.selIndex;
        config.selItem = selIndex;
        config.itemData[selIndex] = configItem;

        config.proxy = null;
        table.assign(config,configItem);

        config.quickRef = frmSetting.chkQuickRef.checked;
        config.save();

        frmSetting.endModal();

        if(!wb.started()){
            resetMessages();
        }

        thread.delay(100)
        winform.editPrompt.setFocus();
    }

    frmSetting.btnEdit.oncommand = function(id,event){
        listEdit.beginEdit();
    }

    frmSetting.btnAdd.oncommand = function(id,event){
        listEdit.beginEdit(0);
    }

    frmSetting.btnRemove.oncommand = function(id,event){
        if(frmSetting.lstConfig.count==1){
            return frmSetting.msgboxErr("只有一个配置方案时不允许删除！");
        }

        var selIndex = frmSetting.lstConfig.selIndex;
        frmSetting.lstConfig.delete(selIndex)

        frmSetting.lstConfig.selIndex = selIndex<=frmSetting.lstConfig.count ? selIndex : selIndex -1;
        frmSetting.lstConfig.onSelChange()
    }

    listEdit.onEditChanged = function(newText,selIndex){
        config.itemNames = frmSetting.lstConfig.items;

        frmSetting.lstConfig.selIndex = selIndex;
        frmSetting.lstConfig.onSelChange();

        config.save();
    }

    frmSetting.btnAdd.skin({
        color={
            active=0xFF00FF00;
            default=0xFF3C3C3C;
            disabled=0xFF6D6D6D;
            hover=0xFFFF0000
        }
    })

    frmSetting.btnRemove.skin({
        color={
            active=0xFF00FF00;
            default=0xFF3C3C3C;
            disabled=0xFF6D6D6D;
            hover=0xFFFF0000
        }
    })

    frmSetting.btnEdit.skin({
        color={
            active=0xFF00FF00;
            default=0xFF3C3C3C;
            disabled=0xFF6D6D6D;
            hover=0xFFFF0000
        }
    })

    frmSetting.doModal(winform);
}

winform.chkFix.checked = true;
winform.chkFix.oncommand = function(id,event){
    var md = wb.getMarkdown();
    if(owner.checked){
        md = ide.aifix.markdown(md,true)
    }

    wb.write(md);
}

wb.write("
- 打开此工具可自动获取编辑器选中代码块，并生成提示词�?- 在编辑器选中代码块，�?`Shift + F1` 可打开此工具。注意不要在放开 `F1` 前放开 `Shift` 键�?- 按住 `Ctrl`键点 `复制` 按钮可复�?AI 最后一次输出的代码块�?- 请注意查看下面提示词输入框的右键菜单�?- 本工具支持联网自动读�?aardio 文档，复�?aardio 在线文档链接会自动插入提示词�?- [点这里开�?VIP 专属技术支持服务](https://aardio.com/vip)
")

//获取 IDE 中当前选中的代�?import ide;
var codeEditor = ide.getActiveCodeEditor();
if(codeEditor){
    var selText = codeEditor.selText;
    if(selText){
        selText = '解释代码：\r\n\r\n``````aardio\r\n' + selText + '\r\n``````';
        winform.editPrompt.text = string.crlf(selText);
    }
}

//默认设置输入框焦�?winform.editPrompt.setFocus();

import win.clip.viewer;
var clipViewer = win.clip.viewer(winform)
clipViewer.onDrawClipboard=function(){
     var text = win.clip.read();
     if(text && ( string.match(text,"^%\[\]%()$")
         || string.startWith(text,"https://www.aardio.com/zh-cn/doc") ) ){
        if(!#winform.editPrompt.text) winform.editPrompt.text = '\n';
        winform.editPrompt.appendText('\n',text);
     }
}
clipViewer.onDrawClipboard();

//打开 AI 搜索
winform.promptTool.link = "https://www.aardio.com/zh-cn/doc/?q=/zh-cn/ai/prompt/"
winform.promptTool.onHyperlinkClick = function(nmSysLink,url,id,index){
    var q = winform.editPrompt.text;
    if(#q){
        import inet.url;
        raw.execute("https://www.aardio.com/zh-cn/ai/prompt/?q="+inet.url.encode(q));
    }
    else {
        raw.execute(url);
    }
}

//拆分界面
winform.splitter.split(winform.wndBrowser,winform.editPrompt);

winform.editPrompt.enablePopMenu(function(){
    return {
        { /*分隔�?/ };
        { "插入 aardio 语法速览";  function(id){
            winform.editPrompt.selText = " [aardio 语法速览](https://www.aardio.com/zh-cn/doc/guide/language/syntax-quick-ref.html) "
        }; 0};
        { "插入 aardio 模式匹配语法文档";  function(id){
            winform.editPrompt.selText = " [aardio 模式匹配语法](https://www.aardio.com/zh-cn/doc/library-guide/builtin/string/patterns.html) "
        }; 0};
        { "插入 web.view 使用指南（网页相关）";  function(id){
            winform.editPrompt.selText = " [web.view 使用指南](https://www.aardio.com/zh-cn/doc/library-guide/std/web/view/_.html) "
        }; 0};
        { "插入 web.rest 使用指南（HTTP 相关�?;  function(id){
            winform.editPrompt.selText = " [web.rest 使用指南](https://www.aardio.com/zh-cn/doc/library-guide/std/web/rest/client.html) "
        }; 0};
        { "插入 多线程开发入�?;  function(id){
            winform.editPrompt.selText = " [多线程开发入门](https://www.aardio.com/zh-cn/doc/guide/language/thread.html) "
        }; 0};
        { "插入 高级选项卡指南（多窗口）";  function(id){
            winform.editPrompt.selText = " [高级选项卡指南](https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/tabs/_.html) "
        }; 0};
        { "插入 plus 控件使用指南（界面美化）";  function(id){
            winform.editPrompt.selText = " [plus 控件使用指南](https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/ctrl/plus.html) "
        }; 0};
        { "插入 自定义控件使用指南（界面模块化）";  function(id){
            winform.editPrompt.selText = " [自定义控件使用指南](https://www.aardio.com/zh-cn/doc/library-guide/std/win/ui/ctrl/custom.html) "
        }; 0};
        { "插入 超级热键文档";  function(id){
            winform.editPrompt.selText = " [超级热键使用指南](https://www.aardio.com/zh-cn/doc/library-guide/std/key/hotkey.html) "
        }; 0};
        { "检索相�?aardio 文档";  function(id){
            var q = winform.editPrompt.selText;
            if(#q){
                import inet.url;
                raw.execute("https://www.aardio.com/zh-cn/ai/prompt/?q="+inet.url.encode(q));
            }
        }; !owner.canCopy() ? 1/*_MF_GRAYED*/ : 0};

        { "AI 搜索";  function(id){
            var q = winform.editPrompt.selText;
            if(#q){
                import inet.url;

                var url = inet.url.appendExtraInfo("http://api.aardio.com/search",{
                    q = '```aardio \n' + q + '\n```';
                })
                raw.execute(url);
            }
        }; !owner.canCopy() ? 1/*_MF_GRAYED*/ : 0};
    }
})

global.onError = function( err,over ){
    if(!over){
        import debug;
        var stack = debug.traceback(,"调用�?,3);
        err = string.concat(err,stack);
    }

    if( _STUDIO_INVOKED ) {
        import win;
        win.msgboxErr(err);
    }
}

winform.spinMaxTokens.buddy = winform.editMaxTokens;
winform.spinMaxTokens.setRange(1,1024*8);
winform.spinMaxTokens.pos = config.maxTokens || 1024;
winform.spinMaxTokens.inc = 1024;
//按钮外观样式
winform.btnClear.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF999999;
        hover=0xFFFF0000
    }
})

//按钮外观样式
winform.btnSend.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF999999;
        hover=0xFFFF0000
    }
})

//按钮外观样式
winform.btnSetting.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF999999;
        hover=0xFFFF0000
    }
})

winform.btnCopy.skin({
    color={
        active=0xFF00FF00;
        default=0xFF3C3C3C;
        disabled=0xFF999999;
        hover=0xFFFF0000
    }
})

winform.chkFix.skin({
    color={
        active=0xFF00FF00;
        default=0xFF000000;
        disabled=0xFF999999;
        hover=0xFFFF0000
    };
    checked={
        iconText='\uF14A';
        color={
            active=0xFF00FF00;
            default=0xFF000000;
            disabled=0xFF999999;
            hover=0xFFFF0000
        };
    }
})

winform.beforeDestroy = function(){
    config.maxTokens = winform.spinMaxTokens.pos;
}

winform.show();
win.loopMessage();

```````

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Web/REST/aiChat.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Web/REST/aiChat.md')

