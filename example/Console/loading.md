[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程�?- 加载动画与进�?
```aardio aardio
//控制台程�?- 加载动画与进�?import console;
import console.progress;
var bar = console.progress();
for(i=1;100; 1){
    bar.setProgress(i,i +"% loading ......");
    sleep(30)
}

console.showLoading("loading",,console.color.yellow);
sleep(1000)
console.log("调用 console.log 等可以自动打开控制台的函数都可以自动关闭console.showLoading 函数创建的动�?)

//感谢 nlysh 收集�?dotTable
var dotTable = {
    {"   ";".  ";".. ";"...";"....";"......";interval=200};
    {"�?";"�?";"�?";"─ "};
    {"�?";"╀ ";"�?";"�?"};
    {"�?;"�?;"�?;"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?;"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?;"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?};
    {"=    ";" ==  ";" === ";" ====";"  ===";"   ==";"    =";""};
    {"�?    ";" �?   ";"  �?  ";"   �? ";"    �?";"     �?;"    �?";"   �? ";"  �?  ";" �?   "};
    {">))'>    ";"�?))'>   ";" �?))'>  ";"  �?))'> ";"   �?))'>";"   �?'((<";"  �?'((< ";" �?'((<  ";" <'((<   ";"<'((<    "};
    {"�?";"�?";"�?";"�?"};
    {"�?";"�?";"�?";"�?"};
    {"�?";"�?";"�?";"�?"};
    {"�?";"�?";"�?";"�?"};
    {"�?";"�?";"�?";"�?"};
    {"�?";"�?";"�?";"�?"};

    {" ▹▹▹▹";"�?▹▹�?;"▹▹ ▹▹";"▹▹�?�?;"▹▹▹▹ "};
    {"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?;"�?;"�?};
    {"◇◇�?;"◈◇�?;"◇◈�?;"◇◇�?};
    {"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?;"�?;"�?;"�?;"�?;"�?;"�?};
    {"�?;"�?;"�?;"�?;"�?;"�?;"�?;"�?;"�?};
    {"�?";"�?";"�?";"�?"};
    {"�?;"�?;"�?};
}

console.setLoadingDots(dotTable[1],true);
for(i=1;15;1){
    console.showLoading(i + "% loading ");
    sleep(50);
}

console.pause(true);

```

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Console/loading.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ���?'))window.location='https://www.aardio.com/zh-cn/doc/example/Console/loading.md')
