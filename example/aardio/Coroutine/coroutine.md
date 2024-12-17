[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 瀵圭О寮忓崗绋?
```aardio aardio
//瀵圭О寮忓崗绋?import console;
import coroutine;

class 鍏徃 {

     ctor(){
        var coroutine = ..coroutine;

        this.瀹㈡湇 = coroutine.create(
            function(宸ュ崟){

                while(宸ュ崟){
                    宸ュ崟 = coroutine.transfer(this.鐢ㄦ埛,"宸茶В鍐?" + 宸ュ崟)
                }

                coroutine.transfer( ,"鑰佹澘,绱緱涓嶅鐙?缁欏姞鐝垂涓嶏紵!")
            }
        )

        this.鐢ㄦ埛 = coroutine.create(
            function(娑堟伅){

                for(i=1;100;1){
                    ..console.log(  coroutine.transfer(this.瀹㈡湇,"宸ュ崟鍙?" + i) );
                }

                coroutine.transfer(this.瀹㈡湇)
            }
        )

        ..console.log( coroutine.transfer( this.鐢ㄦ埛,"娆㈣繋鍏変复,鏈変换浣曢棶棰樿鑱旂郴瀹㈡湇") );
    }
}

coroutine.run(鍏徃)
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/aardio/Coroutine/coroutine.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/aardio/Coroutine/coroutine.md')

