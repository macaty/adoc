[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵撳紑淇濆瓨RTF鏂囦欢

```aardio aardio
//瀛樺彇RTF鏂囦欢
import win.ui;
/*DSG{{*/
var winform = win.form(text="鎵撳紑淇濆瓨RTF鏂囦欢";right=599;bottom=399)
winform.add(
richedit={cls="richedit";left=18;top=10;right=586;bottom=387;db=1;dl=1;dr=1;dt=1;edge=1;hscroll=1;multiline=1;vscroll=1;z=1}
)
/*}}*/

//鐩存帴鍐欏叆RTF
winform.richedit.streamIn(`{\rtf1\ansi\ansicpg936\deff0\nouicompat\deflang2052\deflangfe2052{\fonttbl{\f0\fnil\fcharset134 \'cb\'ce\'cc\'e5;}}
{\*\generator Riched20 10.0.18362}{\info{\horzdoc}{\*\lchars ([\'7b\'a1\'a4\'a1\'ae\'a1\'b0\'a1\'b4\'a1\'b6\'a1\'b8\'a1\'ba\'a1\'be\'a1\'b2\'a1\'bc\'a3\'a8\'a3\'ae\'a3\'db\'a3\'fb\'a1\'ea\'a3\'a4}{\*\fchars !),.:;?]\'7d\'a1\'a7\'a1\'a4\'a1\'a6\'a1\'a5\'a8D\'a1\'ac\'a1\'af\'a1\'b1\'a1\'ad\'a1\'c3\'a1\'a2\'a1\'a3\'a1\'a8\'a1\'a9\'a1\'b5\'a1\'b7\'a1\'b9\'a1\'bb\'a1\'bf\'a1\'b3\'a1\'bd\'a3\'a1\'a3\'a2\'a3\'a7\'a3\'a9\'a3\'ac\'a3\'ae\'a3\'ba\'a3\'bb\'a3\'bf\'a3\'dd\'a3\'e0\'a3\'fc\'a3\'fd\'a1\'ab\'a1\'e9}}
\viewkind4\uc1
\pard\widctlpar\sa200\sl276\slmult1\b\f0\fs22 test\b0\par
}`)

//鐩存帴鍐欏叆RTF鏂囦欢
//winform.richedit.streamIn(,`/res/test.rtf`)

import fsys.dlg;
var path = fsys.dlg.open("*.rtf|*.rtf||","鎵撳紑RTF鏂囦欢");

if( path ){

    //鏂囦欢娴佸啓鍏?    var file = io.file(path,"r+b");
    winform.richedit.streamIn( ,function(format,buf,len){
        return 0,file.readBuffer(buf,len):0;
    } )
    file.close()

    //鏂囦欢娴佽緭鍑?    var file = io.file("/test.rtf","w+b")
    winform.richedit.streamOut( ,function(format,buf,len){
        return 0,file.writeBuffer(buf,len) : 0;
    } )
    file.close()
}

winform.show()
win.loopMessage();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Windows/Edit/richedit_change.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Windows/Edit/richedit_change.md')

