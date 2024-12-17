[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎺у埗鍙扮▼搴?- 鍝嶅簲鎸夐敭

```aardio aardio
//鎺у埗鍙扮▼搴?- 鍝嶅簲鎸夐敭

import key;
import console;

console.log("鎸塃SC閫�鍑?)
while(true){
    if( console.kbHit() ){
        var kb = console.kbRead();
        if(!kb) continue;
        if(kb.bKeyDown) continue;

        if( kb.wVirtualKeyCode == 0x1B/*_VK_ESC*/ ){
            break;
        }
        else {
            io.print( key.getName( kb.wVirtualKeyCode), kb.bKeyDown? "鎸変笅" : "寮硅捣")
        }
    }
}

console.close();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/kb.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/kb.md')

