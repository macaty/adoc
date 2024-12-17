[aardio 鏂囨。](../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎺у埗鍙扮▼搴忚寖渚?- 鑷畾涔夐鑹?
```aardio aardio
//鎺у埗鍙扮▼搴忚寖渚?- 鑷畾涔夐鑹?
import console;
console.setTitle("鑷畾涔夋帶鍒跺彴棰滆壊");

//淇敼鏁翠釜鎺у埗鍙扮殑棰滆壊
for(name,clr in console.color){
    console.setColor(0xF-clr, clr);
    console.log("鏉ユ潵鎴戞槸涓�涓彔鑿?,name);
    sleep(100);
}

console.setColor();
console.pause();

//浠呬慨鏀规枃鏈尯鐨勫墠鏅壊涓庤儗鏅壊
for(name,clr  in console.color){
    console.setTextAttribute(0xF-clr, clr);
    console.log("鏉ユ潵鎴戞槸涓�涓彔鑿?,name);
    sleep(100);

}
console.setTextAttribute();

//浠呬慨鏀硅緭鍑烘枃鏈殑棰滆壊锛屽苟涓旀仮澶嶉粯璁や箣鍓嶇殑棰滆壊銆?console.writeColorText("鏂囨湰",console.color.yellow,console.color.darkGray);

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/ColorConsole.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/ColorConsole.md')

