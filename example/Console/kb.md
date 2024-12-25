[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程�?- 响应按键

```aardio aardio
//控制台程�?- 响应按键

import key;
import console;

console.log("按ESC退�?)
while(true){
    if( console.kbHit() ){
        var kb = console.kbRead();
        if(!kb) continue;
        if(kb.bKeyDown) continue;

        if( kb.wVirtualKeyCode == 0x1B/*_VK_ESC*/ ){
            break;
        }
        else {
            io.print( key.getName( kb.wVirtualKeyCode), kb.bKeyDown? "按下" : "弹起")
        }
    }
}

console.close();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Console/kb.md)

