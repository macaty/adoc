[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: torrent文件解析演示

```aardio aardio
//解析torrent文件
import win.ui;
/*DSG{{*/
var winform = win.form(text="torrent文件解析演示";right=661;bottom=636;border="dialog frame";max=false)
winform.add(
edit={cls="edit";left=19;top=37;right=646;bottom=618;autohscroll=false;edge=1;hscroll=1;multiline=1;vscroll=1;z=1};
static={cls="static";text="请拖�?*.torrent 文件到当前窗�?;left=21;top=9;right=476;bottom=33;transparent=1;z=2}
)
/*}}*/

import crypt;
import inet.url;
import bencoding;
import string.conv.pinyin;
import fsys.dlg;

var updateTorrentName = function(filePath){
    winform.edit.print( io.splitpath(filePath).file );
    var decoder = bencoding.decoder(string.load(filePath))
    var torrent = decoder.parse()

    if(torrent.info["name.utf-8"]){
        winform.edit.print(`info["name.utf-8"]：`,torrent.info["name.utf-8"])
        torrent.info["name.utf-8"] = string.replace(torrent.info["name.utf-8"],":",function(str){
            var py = string.conv.pinyin(str);
            if(py && py!=str){ return py[[1]];  }
        })
        winform.edit.print("已更改为�?,torrent.info["name.utf-8"])
    }

    if(torrent.info["name"]){
        winform.edit.print(`info["name"]：`,torrent.info["name"])
        torrent.info["name"] = string.replace(torrent.info["name"],":",function(str){
            var py = string.conv.pinyin(str);
            if(py && py!=str){ return py[[1]];   }
        })
        winform.edit.print("已更改为�?,torrent.info["name"])
    }

    var magnet = 'magnet:?'+ "xt=urn:btih:"
        + ..crypt.sha1( decoder.getString( torrent[["info"]]) ,true)
        + "&" +..inet.url.stringifyParameters({
            dn = torrent['info']['name'];
            tr = torrent['announce'];
            xl = torrent['info']['length']
        },false)
    winform.edit.print(magnet);

    var savePath = fsys.dlg.save("*.torrent|*.torrent|","保存已更改的torrent文件",,winform);
    if(!savePath){ return; }

    var encoder = bencoding.encoder()
    var bin = encoder.stringify(torrent);
    string.save(savePath, bin)
}

winform.onDropFiles = function(files){
    for i,path in table.eachIndex(files){
        if(string.endWith(path,".torrent",true)){
            updateTorrentName(path);
        }
    }
}

winform.show();
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/File/torrent/bencoding.md)

