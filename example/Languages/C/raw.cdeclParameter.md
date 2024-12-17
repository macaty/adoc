[aardio 鏂囨。](../../../index.htm "aardio 缂栫▼璇█鏂囨。棣栭〉")

# aardio 鑼冧緥: 璋冪敤 C 璇█ - 缁撴瀯鍖栧弬鏁拌〃

```aardio aardio
//aardio 璋冪敤 C 璇█ - 缁撴瀯鍖栧弬鏁拌〃

import tcc;
var c = tcc();
c.enableIoPrintf();

c.code = /****
    #include <stdio.h>
    #include <stdlib.h>

    //鍦–璇█涓畾涔?raw.cdeclParameter,娉ㄦ剰 aardio 瀛楃涓查粯璁や负 UTF8 缂栫爜
    typedef struct{
        const char *(__cdecl *getType) (const char * name);
        void * (__cdecl *getFunction) (const char * name,const char *proto);
        void (__cdecl *setFunction) (const char * name,const char *proto,void * addr);
        const char *(__cdecl *getBinary) (const char * name,unsigned int *size);
        void (__cdecl *setBinary) (const char * name,char * value,unsigned int size);
        const char *(__cdecl *getString) (const char * name);
        void (__cdecl *setString) (const char * name,const char * value);
        void (__cdecl *getNumber) (const char * name,double * value);
        void (__cdecl *setNumber) (const char * name,double value);
        unsigned long long (__cdecl *getSize64) (const char * name);
        void (__cdecl *setSize64) (const char * name,unsigned long long value);
        void * (__cdecl *getPointer) (const char * name);
        void (__cdecl *setPointer) (const char * name,void * value);
        int (__cdecl *callString) (const char * name,const char * arg);
        int (__cdecl *callNumber) (const char * name,double arg);
        int (__cdecl *call) (const char * name);
        unsigned int(__cdecl *len)(const char * name);
    } aardioParameter;

    typedef double (*ADDFUNC) (double a,double b);

    int func_c ( aardioParameter * opt )
    {

        //鍙栧弬鏁颁腑鐨勫瓧娈靛�?瀛楁鍚嶅彲浠ヤ娇鐢ㄥ悕瀛楃┖闂?渚嬪  x.y.z.瀛楁鍚?        const char * s = opt->getString("hello");
        io_printf( "Hello! 鎴戞槸C璇█浠ｇ爜\n鏀跺埌aardio浼犳潵鐨勫弬鏁?%s\n", s );

        //璋冪敤鍙傛暟涓寘鍚殑鍑芥暟鍚?        opt->callString("func","鍙傛暟");

        //鍙互娣诲姞C鍑芥暟涓?aardio 鍑芥暟
        opt->setFunction("test.printf","void(string s,int x,int y)",printf);

        //涔熶互澹版槑aardio涓殑鍑芥暟涓篊鍑芥暟
        int (*add) (int a,int b) =  opt->getFunction("test.add","int(int,int)" );
        int c = (*add)(12,3);

        unsigned long long  x =  opt->getSize64("size" );
        io_printf( " LONG64: %I64u\n", x);
        return 0;
    }

****/

//鍒涘缓缁撴瀯鍖栧弬鏁?import console;
import raw.cdeclParameter;
var cdeclParameter = raw.cdeclParameter(
    size = ..math.size64(2,1);
    hello = "娴嬭瘯!";
    func = function(鍙傛暟){
        ..console.log("aardio鍑芥暟琚洖璋冧簡",鍙傛暟 )
    }
    test = {
        add  = function(a,b){
            owner.printf( '鍦╝ardio涓皟鐢–璇█澹版槑鐨勫嚱鏁?%d %d\n',12,33 );
            return a+b
        }
    }
)

//鑾峰彇C鍑芥暟
func_c = c.getCdecl("func_c","int(struct msg)")

//璋冪敤C鍑芥暟
func_c( cdeclParameter )

//鍏抽棴C璇█缂栬瘧鍣?c.close();

console.pause();

```

[Markdown 鏍煎紡](javascript:if(confirm('https://www.aardio.com/zh-cn/doc/example/Languages/C/raw.cdeclParameter.md  \n\n该文件无法用 Teleport Ultra 下载, 因为 它不在项目文件类型规范内。  \n\n你想在服务器上打开它?'))window.location='https://www.aardio.com/zh-cn/doc/example/Languages/C/raw.cdeclParameter.md')

