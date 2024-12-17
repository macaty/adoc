[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: Hasher - 鏂囦欢鍝堝笇宸ュ叿

```aardio aardio
//鏂囦欢鍝堝笇宸ュ叿
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio Hasher - 鏂囦欢鍝堝笇宸ュ叿";right=479;bottom=300;acceptfiles=1;topmost=1)
winform.add(
progress={cls="progress";left=8;top=283;right=472;bottom=293;db=1;dl=1;dr=1;edge=1;font=LOGFONT(name='瀹嬩綋');max=100;min=0;z=1};
richedit={cls="richedit";left=8;top=25;right=472;bottom=273;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='瀹嬩綋');multiline=1;readonly=1;vscroll=1;wrap=1;z=2};
static={cls="static";text="璇蜂粠澶栭儴鎷栧姩鏂囦欢鍒颁笅闈㈢殑鏂囨湰妗嗕腑:";left=13;top=5;right=336;bottom=21;dt=1;transparent=1;z=3}
)
/*}}*/

import crypt;
winform.onDropFiles = function(files){
    for (k,path in files ) {
        var file,err =  io.file(path, "rbR");//R 闅忔満浼樺寲
        if(!file) {
            winform.richedit.appendText( "鎵撳紑鏂囦欢澶辫触:" , path , '\n',err , '\n' );
            return;
        }
        winform.richedit.appendText( "姝ｅ湪璁＄畻鍝堝笇鍊?" , path , '\n');

        var crc32;
        var md5 = crypt().createHashByMd5();
        var sha1 = crypt().createHashBySha1();
        var sha256 = crypt(,0x18/*_PROV_RSA_AES*/).createHashBySha256();

        var bufsize = 0xA00000;
        winform.progress.setRange( 0,file.size()/bufsize );
        winform.progress.pos = 0;

        while(
            var buffer,readSize = raw.buffer( bufsize );
            readSize = file.readBuffer(buffer); //璇绘枃浠?            readSize
        ) {
            md5.hashBuffer(buffer,readSize);
            sha1.hashBuffer(buffer,readSize);
            sha256.hashBuffer(buffer,readSize);
            crc32 = string.crc32(buffer,crc32,readSize);

            win.peekPumpInputMessage();
            winform.progress.stepIt();
        }
        file.close();
        winform.progress.stepIt();

        winform.richedit.print('MD5:' , md5.getHexValue() );
        winform.richedit.print('SHA1:', sha1.getHexValue() );
        winform.richedit.print('SHA256:', sha256.getHexValue() );
        winform.richedit.printf('CRC32:\t%X', crc32 );
        winform.richedit.print();

        md5.destroy();
        sha1.destroy();
        sha256.destroy();
    }
}

winform.show();
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Text/Hash/hashfile.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Text/Hash/hashfile.md')

