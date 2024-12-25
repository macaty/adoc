[aardio 文档](../../../index.htm "aardio 编程语言文档首页")

# aardio 范例: 对称式协�?
```aardio aardio
//对称式协�?import console;
import coroutine;

class 公司 {

     ctor(){
        var coroutine = ..coroutine;

        this.客服 = coroutine.create(
            function(工单){

                while(工单){
                    工单 = coroutine.transfer(this.用户,"已解�?" + 工单)
                }

                coroutine.transfer( ,"老板,累得不如�?给加班费不？!")
            }
        )

        this.用户 = coroutine.create(
            function(消息){

                for(i=1;100;1){
                    ..console.log(  coroutine.transfer(this.客服,"工单�?" + i) );
                }

                coroutine.transfer(this.客服)
            }
        )

        ..console.log( coroutine.transfer( this.用户,"欢迎光临,有任何问题请联系客服") );
    }
}

coroutine.run(公司)
console.pause();

```

[Markdown 格式](https://www.aardio.com/zh-cn/doc/example/aardio/Coroutine/coroutine.md)

