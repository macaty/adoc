[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: main

```aardio aardio
import console;

//缂栬瘧 proto鏂囦欢,鐢熸垚绫诲簱
import protobuf.parser;
if(!protobuf.parser)
    return;

var p = protobuf.parser();
p.parseFile("\res\test.proto",,false)

//瀵煎叆鐢熸垚鐨勭被搴?import AddressBook
import Person

//璇诲彇鏁版嵁鏂囦欢
book = AddressBook();
var str = string.load("\res\test.pb" );
book.parseFromString(str);

//閬嶅巻鎵�鏈夊瓧娈?for k,v in book.eachName(){
    console.log(k,v)
}

//鏀寔杞崲涓?JSON
console.dumpJson(book)

//璁块棶鏁扮粍鍏冪礌
person = book.person[1]
console.log("鐢ㄦ埛鍚?,person.name );
console.log(person.id );
console.log(person.email );
console.log("鐢佃瘽鍙风爜鏁扮洰",#person.phone );
console.log("-------------------")

person = book.person[2]
console.log("鐢ㄦ埛鍚?,person.name );
console.log(person.id );
console.log(person.email );
console.log("鐢佃瘽鍙风爜鏁扮洰",#person.phone );

//閬嶅巻鏁扮粍锛岀敤 # 鎿嶄綔绗﹀彇鏁扮粍闀垮害
for( i=1;#person.phone ){
    console.log(i,person.phone[i].number )
}
console.log("-------------------")

console.log("璇峰彸閿偣鍑?宸ョ▼->鐢ㄦ埛搴?,鍦ㄥ脊鍑鸿彍鍗曚腑鐐瑰嚮'鍒锋柊鐩綍' ")
console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Network/protobuf/SampleProjects/main.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 服务器报告访问的文件是隐藏的。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Network/protobuf/SampleProjects/main.md')

