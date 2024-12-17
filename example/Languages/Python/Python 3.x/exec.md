[aardio 鏂囨。](../../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 鎵ц Python 浠ｇ爜

```aardio aardio
//aardio 鎵ц Python 浠ｇ爜
import console.int;
import py3;

py3.main.testData = "鍙互杩欐牱棰勫厛鎸囧畾 Python 鍏ㄥ眬鍙橀噺";

//Python 浠ｇ爜锛屾敞鎰?Python 瀵圭┖鏍兼湁涓ユ牸瑕佹眰锛屼贡鎸夌┖鏍兼姤閿欎笉鏄?bug銆?var pyCode = /**
def getList(a,b):
    return [a,b,testData] # 杩斿洖鍒楄〃
    #return a,b,testData # Python 澶氳繑鍥炲�煎疄闄呮槸杩斿洖涓�涓?tuple
**/

/*
鎵ц Python3 鐨勪唬鐮侊紝
濡傛灉鍙傛暟 pyCode 涓虹被浼?"/res/py.aardio" 杩欐牱鐨?aardio 浠ｇ爜璺緞锛?鍒欐敮鎸佹ā鏉胯娉曪細 https://www.aardio.com/zh-cn/doc/language-reference/templating/syntax.html
*/
py3.exec( pyCode )

//浠?py3.main 妯″潡璋冪敤 Python 浠ｇ爜瀹氫箟鐨勫嚱鏁?var pyList = py3.main.getList(12,23);

//list 鎴?tuple 鍙敤涓嬫爣璁块棶锛孭ython 瀵硅薄璧峰绱㈠紩涓?0锛宎ardio 鏁扮粍璧峰绱㈠紩涓?1銆?var num = pyList[0];

//鍙互濡備笅閬嶅巻 pyObject 瀵硅薄銆?for( pyItem in pyList.each() ){
    console.log(pyItem) //鍩虹绫诲瀷宸茶浆鎹负绾?aardio 鍊硷紝鍏朵粬涓?py2.object
}

//pyObject 鏀寔 table.eachIndex 鍒涘缓鐨勮凯浠ｅ櫒
for i,pyItem in table.eachIndex(pyList){
    console.log( i,pyItem ) //鍩虹绫诲瀷宸茶浆鎹负绾?aardio 鍊硷紝鍏朵粬涓?py2.object
}

//杞崲涓虹函 aardio 鍊?var list = pyList.parseValue()

console.dump(list);

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/exec.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/Python/Python 3.x/exec.md')

