[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: Hasher - 文件哈希工具

```aardio aardio
//文件哈希工具
import win.ui;
/*DSG{{*/
var winform = win.form(text="aardio Hasher - 文件哈希工具";right=479;bottom=300;acceptfiles=1;topmost=1)
winform.add(
progress={cls="progress";left=8;top=283;right=472;bottom=293;db=1;dl=1;dr=1;edge=1;font=LOGFONT(name='宋体');max=100;min=0;z=1};
richedit={cls="richedit";left=8;top=25;right=472;bottom=273;db=1;dl=1;dr=1;dt=1;edge=1;font=LOGFONT(name='宋体');multiline=1;readonly=1;vscroll=1;wrap=1;z=2};
static={cls="static";text="请从外部拖动文件到下面的文本框中:";left=13;top=5;right=336;bottom=21;dt=1;transparent=1;z=3}
)
/*}}*/

import crypt;
winform.onDropFiles = function(files){
    for (k,path in files ) {
        var file,err =  io.file(path, "rbR");//R 随机优化
        if(!file) {
            winform.richedit.appendText( "打开文件失败:" , path , '\n',err , '\n' );
            return;
        }
        winform.richedit.appendText( "正在计算哈希�?" , path , '\n');

        var crc32;
        var md5 = crypt().createHashByMd5();
        var sha1 = crypt().createHashBySha1();
        var sha256 = crypt(,0x18/*_PROV_RSA_AES*/).createHashBySha256();

        var bufsize = 0xA00000;
        winform.progress.setRange( 0,file.size()/bufsize );
        winform.progress.pos = 0;

        while(
            var buffer,readSize = raw.buffer( bufsize );
            readSize = file.readBuffer(buffer); //读文�?            readSize
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

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Text/Hash/hashfile.md)

