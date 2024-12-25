[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 控制台程�?- 倒计时效�?
```aardio aardio
//控制台程�?- 倒计时效�?import console;

//打开控制�?console.open();

console.stdout.write("tick:",100/*先输入三个字�?/ );

for(i=100;1;-1){
    console.writeBack("%03d",i);//该函数写几格先退几格
    sleep(100)
}

console.print();
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/Console/Countdown.md)

