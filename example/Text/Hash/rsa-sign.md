[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RSA 绛惧悕

```aardio aardio
//RSA 绛惧悕
import win.ui;
/*DSG{{*/
var winform = win.form(text="RSA绛惧悕";right=797;bottom=561)
winform.add(
btnExportPrivatePkcs1Raw={cls="button";text="瀵煎嚭 PKCS#1 绉侀挜";left=29;top=196;right=166;bottom=232;dl=1;dt=1;z=5};
btnExportPrivatePkcs8={cls="button";text="瀵煎嚭 PKCS#8 绉侀挜";left=29;top=87;right=166;bottom=123;dl=1;dt=1;z=4};
btnExportPublicPkcs1Raw={cls="button";text="瀵煎嚭 PKCS#1 鍏挜";left=29;top=141;right=166;bottom=177;dl=1;dt=1;z=3};
btnExportPublicX509={cls="button";text="瀵煎嚭 SPKI 鍏挜";left=29;top=32;right=166;bottom=68;dl=1;dt=1;z=2};
btnImportKey={cls="button";text="瀵煎叆鍏挜鎴栫閽?鑷姩璇嗗埆)";left=418;top=257;right=768;bottom=293;db=1;dr=1;z=6};
btnSign={cls="button";text="绛惧悕(浣跨敤绉侀挜)";left=435;top=509;right=569;bottom=545;db=1;dr=1;z=8};
btnVerify={cls="button";text="楠岃瘉(浣跨敤鍏挜)";left=586;top=509;right=720;bottom=545;db=1;dr=1;z=9};
editKey={cls="richedit";left=190;top=22;right=770;bottom=252;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='鏂板畫浣?);hscroll=1;multiline=1;vscroll=1;z=1};
editSign={cls="edit";left=190;top=302;right=770;bottom=368;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;z=10};
editText={cls="richedit";text="娴嬭瘯鏁版嵁( UTF-8 缂栫爜)";left=29;top=376;right=770;bottom=504;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=7};
static={cls="static";text="绛惧悕:";left=78;top=316;right=174;bottom=337;align="right";db=1;dl=1;transparent=1;z=11}
)
/*}}*/

import crypt.rsa;
var rsa = crypt.rsa();
rsa.genSignatureKey();

winform.btnExportPublicX509.oncommand = function(id,event){
    //瀵煎嚭閫氱敤鐨?SPKI (Subject Public Key Info) 鏍煎紡鍏挜
    winform.editKey.text = rsa.exportPublicKeyX509ToPem();
}

winform.btnExportPublicPkcs1Raw.oncommand = function(id,event){
    winform.editKey.text = rsa.exportPublicKeyPkcs1RawToPem();
}

winform.btnExportPrivatePkcs8.oncommand = function(id,event){
    winform.editKey.text = rsa.exportPrivateKeyPkcs8ToPem();
}

winform.btnExportPrivatePkcs1Raw.oncommand = function(id,event){
    winform.editKey.text = rsa.exportPrivateKeyPkcs1RawToPem();
}

winform.btnImportKey.oncommand = function(id,event){
    var header = rsa.importPemKey(winform.editKey.text);
    if(header) {
        winform.msgbox("宸插鍏ワ細" + header);
    }
    else winform.msgboxErr("閿欒鐨勫瘑閽ユ牸寮?)
}

winform.btnSign.oncommand = function(id,event){

    //SHA256withRSA
    rsa.createHashBySha256(winform.editText.text);
    var sign =  rsa.signToBase64();

    if(!sign) return winform.msgboxErr("绛惧悕澶辫触,璇锋鏌ユ槸鍚﹀鍏ヤ簡姝ｇ‘鐨勭閽?);
    winform.editSign.text = sign;

}

winform.btnVerify.oncommand = function(id,event){

    //SHA256withRSA
    rsa.createHashBySha256(winform.editText.text);
    if( !rsa.verifyFromBase64( winform.editSign.text ) ){
        winform.msgboxErr("绛惧悕鏄敊璇殑,鏁版嵁宸茶绡℃敼,鎴栨湭瀵煎叆姝ｇ‘鐨勫叕閽?);
    }
    else {
        winform.msgbox("绛惧悕鏄纭殑,鏁版嵁鏈绡℃敼");
    }
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Hash/rsa-sign.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Hash/rsa-sign.md')

