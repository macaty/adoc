[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: HTMLayout behavior用法演示

```aardio aardio
//behavior
import win.ui;
/*DSG{{*/
winform = win.form(text="HTMLayout behavior用法演示";right=599;bottom=399;)
winform.add()
/*}}*/

import web.layout;
wbLayout = web.layout(winform);

/*
添加behavior非常简�?
只要�?web.layout.behavior 名字空间下添加库并导入当前程�?或直接添加新的名字空间都可以创建behavior

behavior也可以使用合法的aardio名字空间(该名字空间默认位�?web.layout.behavior 名字空间内部 ),
例如  behaivor:"button.command" 该behavior对应 aardio中的 web.layout.behavior.button.command 名字空间�?CSS的behaivor属性中的名字空间如果包含多级名字空�?也即包含圆点符号)则必须置于引号内部�?
所有HTMLayout窗体可用的事�? 函数名前缀为on....  )�?behavior 中都可以使用
当然, 仅在CSS样式中指定了 behavior 的节点才可以触发对应的事件�?*/
namespace web.layout.behavior.button.command {

    /*
    ltOwner 参数是绑定behavior的节�?
    实际上也就是指定�?behavior:command 的节点对�?
    ltTarget 通常指的是实际触发事件的节点,
    或者根据不同的事件,ltTarget的意义有所不同
    */
    onButtonClick = function (ltTarget,ltOwner,reason,behaviorParams) {
        ltOwner.printf("点击了按�?);
        ltOwner.postEvent("onMyCustomEvent",2);//可以再次触发其他的事�?注意事件应为 web.layout.event.BEHAVIOR 名字空间下的事件或自定义事件
    }

    //自定义事件的参数与onApplicationEvent相同
    onMyCustomEvent = function (ltTarget,ltOwner,reason,behaviorParams) {
        ltOwner.printf("自定义事件onMyCustomEvent被触�?触发参数:%d",reason)
    }

    //CSS脚本中读�?self:value 时触发此回调，第2个返回值返�?value 的�?    onGetValue = function( ltOwner ){
        return true,"Value:onGetValue";
    }

    //CSS脚本中使�?self:value 修改值时触发此回�?    onSetValue = function(  ltOwner,value ){

        return true
    }

    //所有名字不是on前缀的函�?都可以在CSS脚本中直接调�?
    //在CSSS!调用下面的函数时,第一个实参是下面的第二个形参,第一个ltEle参数则是绑定behavior的节点对�?    func = function(ltOwner,a,b,c){
        ltOwner.printf("调用了自定义函数,收到参数 a:%d b:%d c:%s ",a,b,c )
        return "返回新的�?
    }
}

wbLayout.html =/***
<div id="my-button" 属�?"�?>请点击这�?/div>
***/

wbLayout.css = /**
#my-button{
    /*
    behavior名字前加波浪线表示在原来的behavior列表上追�?而不是替换behavior属性�?    可以指定多个behavior,以空格分�?例如下面�?clickable 是一个内建behavior,表示触发 onButtonClick事件而不�?onMouseClick事件�?    */
    behavior:"button.command clickable";
    active-on!:/*类似behavior中的onMouseDown,也即节点切换到active状�?/
        self.func(1,2,self:value), /*CSSS!脚本以逗号分隔语句*/
    ; /*CSSS!脚本以分号表示语句块结束*//
}
**/

winform.show()
win.loopMessage();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/WebUI/HTMLayout/behavior.md)

