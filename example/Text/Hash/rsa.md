[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: RSA 鍔犲瘑瑙ｅ瘑

```aardio aardio
//RSA 鍔犲瘑瑙ｅ瘑
import win.ui;
/*DSG{{*/
var winform = win.form(text="RSA鍔犲瘑銆佽В瀵?;right=794;bottom=553)
winform.add(
btnDecrypt={cls="button";text="瑙ｅ瘑(浣跨敤绉侀挜)";left=585;top=501;right=719;bottom=537;db=1;dr=1;z=9};
btnEncrypt={cls="button";text="鍔犲瘑(浣跨敤鍏挜)";left=434;top=501;right=568;bottom=537;db=1;dr=1;z=8};
btnExportPrivatePkcs1Raw={cls="button";text="瀵煎嚭 PKCS#1 绉侀挜";left=29;top=198;right=166;bottom=234;dl=1;dt=1;z=5};
btnExportPrivatePkcs8={cls="button";text="瀵煎嚭 PKCS#8 绉侀挜";left=29;top=84;right=166;bottom=120;dl=1;dt=1;z=4};
btnExportPublicPkcs1Raw={cls="button";text="瀵煎嚭 PKCS#1 鍏挜";left=29;top=141;right=166;bottom=177;dl=1;dt=1;z=3};
btnExportPublicX509={cls="button";text="瀵煎嚭 SPKI 鍏挜";left=29;top=28;right=166;bottom=64;dl=1;dt=1;z=2};
btnImportKey={cls="button";text="瀵煎叆鍏挜鎴栫閽?鑷姩璇嗗埆)";left=417;top=255;right=767;bottom=291;db=1;dr=1;z=6};
editKey={cls="richedit";left=189;top=18;right=769;bottom=249;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='NSimSun');hscroll=1;multiline=1;vscroll=1;z=1};
editText={cls="richedit";text="娴嬭瘯鏁版嵁( UTF-8 缂栫爜)";left=29;top=299;right=771;bottom=498;db=1;dl=1;dr=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=7}
)
/*}}*/

import crypt.rsa;
var rsa = crypt.rsa();
rsa.genKey();

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
    if(header) winform.msgbox("宸插鍏ワ細" + header);
    else winform.msgboxErr("閿欒鐨勫瘑閽ユ牸寮?)
}

winform.btnEncrypt.oncommand = function(id,event){
    var plaintext = winform.editText.text;
    var ciphertext = rsa.encryptReverse(plaintext);
    if(ciphertext){
        winform.editText.text = crypt.encodeBin(ciphertext);
    }
    else {
        winform.msgboxErr("鍔犲瘑澶辫触,璇锋鏌ユ槸鍚﹀鍏ヤ簡姝ｇ‘鐨勫叕閽?)
    }
}

winform.btnDecrypt.oncommand = function(id,event){
    var ciphertext = crypt.decodeBin(winform.editText.text);
    if(!ciphertext){
        winform.msgboxErr("瑙ｅ瘑澶辫触,璇锋鏌ユ槸鍚﹁緭鍏ヤ簡 Base64 缂栫爜鐨勫瘑鏂?);
        return;
    }

    //涓庡叾浠栫紪绋嬭瑷�浜掗�氬繀椤讳娇鐢?rsa.decryptReverse() 鑰岄潪 rsa.decrypt() 鍑芥暟
    var plaintext = rsa.decryptReverse(ciphertext);
    if(plaintext){
        winform.editText.text = plaintext;
    }
    else {
        winform.msgboxErr("瑙ｅ瘑澶辫触,璇锋鏌ユ槸鍚﹀鍏ヤ簡姝ｇ‘鐨勭閽?)
    }
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Hash/rsa.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Hash/rsa.md')

