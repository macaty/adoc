[aardio 文档](../../index.htm "aardio 编程语言文档首页")

# sys.display 库模块帮助文�?
## sys.display 成员列表

显卡函数库�?
相关的库：sys.monitor, sys.display, sys.ddcci

### sys.display.eachMode()

[返回对象:DEVMODEDISPLAYDEVICEObject](#DEVMODEDISPLAYDEVICEObject)

### sys.display.eachMode(flags,idx)

```aardio aardio
for( devMode in sys.display.eachMode() ){
    if( devMode.pelsWidth > (devMode.pelsWidth > devMode.pelsHeight ? 640 : 480) ){
        /*列出显卡支持的分辨率*/
    }
}

```

### sys.display.enumAdapters(回调函数)

```aardio aardio
sys.display.enumAdapters(
function(info,description,driverVersion){
    /*枚举显卡,info为显卡信�?description为显卡名�?第一个显卡是默认显示
返回true退出枚�?/
})

```

### sys.display.getAdapter()

获取显卡信息

[返回对象:D3DADAPTERIDENTIFIER9Object](#D3DADAPTERIDENTIFIER9Object)

[Markdown 格式](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/library-reference/sys/display.md  \n\n���ļ��޷��� Teleport Ultra ����, ��Ϊ ��������Ŀ�ļ����͹淶�ڡ�  \n\n�����ڷ������ϴ�����?'))window.location='https://www.aardio.com/zh-cn/doc/library-reference/sys/display.md')

